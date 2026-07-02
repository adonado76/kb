---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "GCP Inventario de recursos"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
  - "Inventario de recursos"
source_path: "product/gcp-resource-inventory.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# GCP Inventario de recursos

GCP La función Inventario de recursos de Cloudability le permite generar una lista oficial de los recursos en la nube de GCP que existían y se facturaron durante un período de informe específico. Usted tiene la flexibilidad de construir esta lista a partir de recursos que abarcan múltiples cuentas y elegir entre diferentes medidas (dimensiones y métricas) para hacer aflorar los detalles relevantes para ellas. Esta información, disponible para cada recurso en la nube, unifica la facturación, la utilización y los metadatos descriptivos para ofrecerle una visión más completa del inventario.

## cómo empezar

GCP La función de informes de inventario de recursos debe estar habilitada para su organización de Cloudability. Debe ponerse en contacto con su TAM/CSM/persona de contacto de la cuenta desde Apptio para realizar este trámite. Una vez activado, espere 2-3 días laborables para que los datos empiecen a aparecer en sus informes de inventario.

Medidas de información sobre el inventario

- Las medidas se clasifican en dimensiones, métricas y etiquetas (las etiquetas incluyen las dimensiones de las etiquetas, los grupos de cuentas y las asignaciones empresariales de Cloudability ). Puede incluir hasta 20 columnas en un informe individual.
- Para cada servicio GCP, se admite un conjunto específico de medidas.
- Puede filtrar sus respectivos informes de inventario utilizando cualquiera de las medidas disponibles en esta función.

Indicadores clave de rendimiento en los que se puede hacer clic para filtrarlos rápidamente

Para cada servicio, se mostrarán los KPI en la parte superior del informe para proporcionarle información resumida clave, como Recursos recién lanzados e Instancias sin etiquetar. Puede hacer clic y filtrar el informe Inventario en función de estos KPI para desglosar los datos específicos del informe que está buscando.

Ventanas de fecha de informe de inventario

En el selector de fechas puede elegir el periodo para el que desea ver los datos de inventario de cada servicio. El intervalo máximo permitido para la selección es de 31 días. Al activar esta función, los datos del inventario de recursos se volverán a rellenar al principio del mes en curso. Con el tiempo, los datos de inventario estarán disponibles en una ventana móvil de tres meses. En cualquier momento, podrá acceder a los datos de inventario de recursos del mes en curso junto con los de los dos meses anteriores.

Filtrado estadístico mediante el filtro de visualización

A partir de los datos de inventario generados para un servicio y un periodo de tiempo específicos, ahora puede elegir mostrar un subconjunto de esos datos, ya sea el número x superior o el porcentaje x de recursos en función de la métrica de coste o utilización que prefiera.

Por ejemplo: Inventario de recursos muestra 1000 registros para el servicio Compute durante un periodo de siete días. Puede filtrar aún más esta visualización eligiendo ver sólo el 25% superior de estos recursos, basándose en el Coste (Total). Aplicando este filtro se obtendrían los 250 recursos más importantes en función de su coste (total), ordenados de mayor a menor.

Exportación de informes

si hace clic en Exportar en la parte superior derecha de la tabla de informes, se exportarán todas las columnas de inventario seleccionadas con los filtros aplicados. Sin embargo, para exportar los datos de inventario completos del mes y servicio seleccionados con todas las columnas admitidas, haga clic en el botón Exportar situado en la parte superior derecha del desplegable de filtros de la barra de herramientas de la ficha.

Guardar informes de inventario de recursos

Puede guardar un informe con sus selecciones de fecha, servicio y filtro y compartirlo con otros usuarios de la organización concediéndoles permisos de "Sólo ver" o "Editar". En la parte superior derecha de la barra de herramientas de la interfaz de usuario del inventario de recursos, puede ver una elipse con un icono de tres puntos en el que, si hace clic, se abrirá el menú Acciones del informe con estas opciones.

- **Guardar como informe:** Con esta opción puede guardar una copia de su informe. Esta opción es útil si alguien ha compartido un informe con usted con un acceso de "Sólo Ver" y usted quiere hacer cambios en este informe haciendo su propia copia del mismo. Otro caso de uso de Guardar como informe es para el Informe por defecto. El informe por defecto no puede modificarse, por lo que deberá seleccionar la opción "Guardar como informe" para guardar los cambios realizados en el informe por defecto.
- **Guardar informe:** Esta opción se utiliza para guardar cualquier cambio realizado en el informe creado o compartido con usted con un permiso "Editar"
- **Compartir informe:** Utilizando esta opción, puedes compartir tus informes con otros usuarios de tu organización dándoles permisos de "Sólo ver" o "Editar".
- **Borrar informe:** Puede eliminar su informe haciendo clic en Eliminar informe.
- **Gestión del intervalo de fechas de los informes guardados:** Los informes guardados con intervalos de fechas no acumulativos no admitidos (superiores a tres meses) se cargarán con el intervalo de fechas restablecido a los 7 días predeterminados. También se mostrará al usuario un mensaje de aviso indicando que se ha restablecido el intervalo de fechas. Esta función garantiza que se pueda seguir accediendo a los informes guardados incluso cuando los intervalos de fechas en los que están almacenados superen el límite permitido.

Nota:

- El número máximo de informes que se mostrarán en el desplegable Informes guardados es 100.
- Cuando se comparta un informe con un usuario, no se enviarán notificaciones por correo electrónico.
- El inventario de recursos admite un máximo de 3 meses de datos, es decir, el mes hasta la fecha + los 2 últimos meses. Así, los datos acabarían caducando en los informes cuando superasen este periodo de conservación.

Utilización del inventario de recursos

1. Para acceder al inventario de recursos de GCP, vaya a Insights > Inventario de recursos y haga clic en la pestaña GCP.

1. Seleccione en el menú desplegable Servicios el servicio cuyo inventario de recursos desea consultar.
2. Seleccione el intervalo de fechas para el que desea ver los datos del inventario de recursos. Puedes elegir ver hasta 31 días de datos como máximo. Los datos mostrados se ordenarán por Coste (Total) en orden descendente por defecto.
3. Haga clic en cualquiera de los KPI con la barra azul de la izquierda para filtrar sus informes en función de ese KPI específico.
4. Haga clic en el botón de configuración de la tabla en la parte superior derecha de la tabla de inventario de recursos para configurar las medidas y etiquetas que desea que se muestren como columnas en la tabla.

Las medidas y etiquetas seleccionadas se muestran como columnas en la tabla.

1. Haga clic en Filtros para aplicar cualquier filtro a su informe de inventario.
2. Utilice el menú desplegable Mostrar situado encima de la tabla Detalles del inventario de recursos para especificar el porcentaje superior o inferior de filas que se mostrarán en la tabla y para ordenar la tabla de forma descendente por la métrica de coste o utilización preferida.
3. Haga clic en el botón Exportar situado en la parte superior derecha de la tabla Detalles del inventario de recursos para exportar todas las columnas que aparecen en la tabla filtradas según su configuración de filtros. Para exportar todos los datos de inventario del mes y servicio seleccionados con todas las columnas soportadas, pulse el botón Exportar, a la derecha del desplegable Filtros en la barra de herramientas de la pestaña.

Medidas de recursos que muestran "No disponible

Para algunos recursos, es posible que algunas medidas, como Fecha de lanzamiento, Estado y Tamaño, entre otras, aparezcan como No disponibles en el informe Inventario de recursos. Esto significa que Cloudability no pudo obtener datos para esas medidas específicas debido a una de las siguientes razones:

- Es posible que no haya realizado credenciales avanzadas para la cuenta a la que pertenecen los recursos concretos.
- La vida útil de los recursos puede haber sido demasiado corta para recoger los datos de esas medidas.
- Las métricas de utilización de estos recursos pueden aparecer como "0" (cero) en el informe.

| GCP Calcular | |
| --- | --- |
| Total de recursos | Número total de recursos en su inventario para el periodo seleccionado. |
| Total de instancias | Número total de instancias de cálculo, excluidas las instantáneas. |
| Recursos recién lanzados | Número de recursos lanzados en el periodo seleccionado. |
| Coste (total) | Coste (total) de las instancias. |
| GCP Disco persistente | |
| Volúmenes totales | Número total de volúmenes en su inventario para el periodo seleccionado. |
| Volúmenes recién lanzados | Número de volúmenes lanzados en el periodo seleccionado. |
| Coste (total) | Coste (total) de todos los volúmenes. |
| Volúmenes no etiquetados | Número de volúmenes que no tienen al menos una etiqueta. |
| Volúmenes desconectados | Número de volúmenes que no están asociados a ninguna instancia de cálculo. |

**Tema principal:** [Inventario de recursos](../product/resource-inventory.html)
