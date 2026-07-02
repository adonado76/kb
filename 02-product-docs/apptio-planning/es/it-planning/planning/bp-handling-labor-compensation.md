---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Buenas prácticas: Tasas de indemnización laboral"
breadcrumb: []
source_path: "it-planning/planning/bp-handling-labor-compensation.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Buenas prácticas: Tasas de indemnización laboral

La información que figura a continuación aborda las consideraciones más comunes a la hora de manejar las tasas de compensación laboral en las aplicaciones de Apptio Planning . Esta información es especialmente relevante para los patrocinadores ejecutivos y las partes interesadas relacionadas antes de que los detalles de la tasa de compensación laboral se registren en las aplicaciones de Apptio Planning .

## Estrategias para los valores de la tasa de retribución del trabajo

Las tasas de retribución de la mano de obra se registran en la tabla de datos de referencia de la mano de obra. Para más detalles sobre la implementación, véase [Gestionar datos de referencia de mano de obra](manage-labor-configuration.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor."). Antes de registrar las tasas de compensación laboral, Apptio recomienda a su organización que adopte un enfoque estándar. A continuación se exponen las estrategias habituales en materia de tasas de retribución del trabajo que deben tenerse en cuenta.

## Valores medios

Esta estrategia utiliza el centro de la horquilla salarial establecida a la hora de vincular los salarios a la mano de obra. Por ejemplo, si la horquilla salarial fuera de 56.000 a 94.000 dólares, el punto medio sería 75.000 dólares.

- Ventaja - Oculta la información salarial a la vista a la vez que proporciona un nivel de datos para mayor claridad.
- Desventaja - El nivel de información de los informes no puede ser exacto al 100%. Se produciría un aumento de las desviaciones, ya que no habría correlación con los datos reales.

## Promedio

Los planes utilizan la media de todos los salarios cuando se integran en un presupuesto más amplio o en un plan de previsiones. Por ejemplo, si tiene 10 analistas, tomaría el salario medio de esos 10 analistas.

- Ventaja - Permite ocultar la información salarial, así como proporcionar una visión estratégica de los datos salariales.
- Desventaja - No permite un enfoque más granular para ver los datos salariales. Se produciría un aumento de las desviaciones, ya que no habría relación con los datos reales.

## Tarifa única

En la pestaña Gastos, los gestores introducen una tarifa única para todos los empleados y los salarios reales. Los gestores son los únicos que pueden verlos si oculta la pestaña Trabajo a los administradores con un rol personalizado. Consulte [Restringir el acceso a los detalles del salario laboral](restrict-access-labor.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados al rol de Administrador. Ver permisos y roles de Frontdoor."). Este es el enfoque recomendado, ya que proporciona la mayor precisión en los datos salariales al tiempo que ofrece cierto nivel de protección.

- Ventaja - Permite una planificación precisa a la hora de elaborar presupuestos o previsiones con respecto a la información salarial. También permite desglosar los informes para obtener una visión más detallada de los datos salariales.
- Desventaja - Los directivos pueden ver toda la información salarial de sus departamentos. Además, estos datos son visibles para el administrador de TBMA o Apptio. Se produciría un aumento de las desviaciones, ya que no habría relación con los datos reales.

## Buenas prácticas: Introducir información salarial por función, región/localización y tipo de empleado (externo frente a interno)

- Ventaja - Enfoque más preciso, menor variación y vinculación con los datos reales.
- Desventaja - Todos los administradores pueden ver la información salarial. Además, cualquier persona con acceso a un Centro de costes específico puede ver todos los salarios de ese Centro de costes.

## Opciones de seguridad laboral

Esta sección describe estrategias para proteger la información laboral dentro de sus entornos Apptio.

## Gestionar permisos de objetos de coste

Muchas empresas establecen permisos detallados para los Objetos de Coste. Estas empresas dedican un esfuerzo considerable a garantizar que los permisos de cada usuario final estén configurados correctamente según el nivel de sus respectivas funciones. Para saber más, consulte [Restringir el acceso a los datos salariales de los trabajadores](restrict-access-labor.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados al rol de Administrador. Ver permisos y roles de Frontdoor.").

## Ocultar información laboral

Dentro de sus respectivos entornos Apptio, en la pestaña Roles, existe la opción de eliminar por completo la opción Labor de los usuarios individuales.

## Seguimiento de la mano de obra fuera de Apptio

Algunas empresas optan por no hacer un seguimiento de la información laboral en sus respectivos entornos Apptio. Estas empresas utilizan otros sistemas para hacer un seguimiento de la información laboral específica y los utilizan conjuntamente con Apptio.

## Restringir el acceso al trabajo a los administradores

La información laboral puede ocultarse a todo el mundo excepto a los administradores, que tendrían que presupuestar toda la mano de obra. Consulte [Restringir el acceso a los detalles del salario laboral](restrict-access-labor.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados al rol de Administrador. Ver permisos y roles de Frontdoor.").

## Permisos de usuario

|  |  |  |
| --- | --- | --- |
| **Nombre del permiso** | **Descripción** | **Funciones por defecto** |
| ITPPlanSettingsEdit | Permite a los usuarios editar la Configuración del Plan. | Se añade por defecto a los roles de **Administrador** y **Propietario del proceso presupuestario**. |
| ITPPlanSettingsView | Permite a los usuarios ver los Ajustes del Plan. | Ninguna |
| ITPCompensationAdjustmentEdit | Permite a los usuarios anular los ajustes de compensación por defecto en las líneas de trabajo para los Ciclos de Compensación definidos. | Se añade por defecto a los roles de **Administrador**, **Propietario de proceso presupuestario** y **Propietario de centro de coste**. |
| ITPCompensationAdjustmentAllPeriodsEdit | Permite a los usuarios editar ajustes de compensación en líneas de trabajo para todos los periodos del plan, incluyendo periodos fuera de los Ciclos de Compensación definidos. | Se añade por defecto al rol de Administrador y Propietario del Proceso Presupuestario. |

Para saber más, consulte [Configuración de los ajustes de las indemnizaciones](plan-labor-compensation.html "Los Propietarios del Proceso Presupuestario o los usuarios con permisos de propietario para un Objeto de Coste pueden contabilizar los ajustes planificados a las tasas de compensación laboral. Esto puede hacerse para el trabajo en curso o previsto. Puede especificar un cambio porcentual en la remuneración base por recurso laboral y la fecha en la que se hará efectivo el cambio.") laborales.
