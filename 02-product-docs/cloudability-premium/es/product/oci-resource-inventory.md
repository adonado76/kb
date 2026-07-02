---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Inventario de recursos de OCI"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
  - "Inventario de recursos"
source_path: "product/oci-resource-inventory.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Inventario de recursos de OCI

La función Inventario de recursos de OCI para Cloudability le permite generar una lista oficial de los recursos de OCI Cloud que existían y se facturaron durante un período de informe específico. Tienes la flexibilidad de crear esta lista a partir de recursos que abarcan varias cuentas y elegir entre diferentes medidas (dimensiones y métricas) para mostrar los detalles relevantes para ellas. En la actualidad, esta información solo está disponible para los recursos **de máquinas virtuales** : unifica la facturación, la utilización y los metadatos descriptivos para ofrecerle una visión más completa del inventario.

## cómo empezar

La función de informes del inventario de recursos de OCI debe estar habilitada para su organización de Cloudability. Debe ponerse en contacto con su TAM/CSM/persona de contacto de la cuenta desde IBM Cloudability para realizar este trámite. Una vez habilitado, espere entre 2 y 3 días hábiles para que los datos comiencen a aparecer en sus informes de inventario.

Medidas de información sobre inventario

- Las medidas se clasifican en dimensiones, métricas y etiquetas (las etiquetas incluyen las dimensiones de etiquetas de Cloudability, los grupos de cuentas y las asignaciones empresariales). Puede incluir hasta 20 columnas en un informe individual.
- Para el servicio OCI Virtual Machine, se admite un conjunto específico de medidas.
- Puede filtrar sus respectivos informes de inventario utilizando cualquiera de las medidas disponibles dentro de esta función.

KPI seleccionables para un filtrado rápido

Para cada servicio, los KPI se mostrarán en la parte superior del informe para proporcionarle información resumida clave, como «Rec ursos totales» e «Instancias sin etiquetar». Puede hacer clic y filtrar el informe de inventario en función de estos KPI para profundizar en los datos específicos del informe que está buscando.

Ventanas de fechas de presentación de informes de inventario

Puede seleccionar el período en el selector de fechas para el que desea ver los datos de inventario de cada servicio. El intervalo máximo permitido para la selección es de 31 días. Al habilitar esta función, los datos del inventario de recursos se rellenarán hasta el comienzo del mes actual. Con el tiempo, los datos de inventario estarán disponibles en un intervalo de tres meses. En cualquier momento, podrá acceder a los datos del inventario de recursos del mes actual, junto con los de los dos meses anteriores.

Filtrado estadístico mediante el filtro de visualización

A partir de los datos de inventario generados para un servicio y un período de tiempo específicos, ahora puede elegir mostrar un subconjunto de esos datos, ya sea el número x superior o el porcentaje x de recursos, según su métrica de coste o utilización preferida.

Por ejemplo: el inventario de recursos muestra 1000 registros para el servicio Compute durante un periodo de siete días. Puede filtrar aún más esta visualización eligiendo ver solo el 25 % superior de estos recursos, según el coste (total). Al aplicar este filtro, se mostrarían los 250 recursos principales según el coste (total), ordenados de mayor a menor.

Exportación de informes

Al hacer clic en Exportar, en la parte superior derecha de la tabla del informe, se exportarán todas las columnas de inventario seleccionadas con los filtros aplicados. Sin embargo, para exportar los datos completos del inventario del mes y el servicio seleccionados con todas las columnas compatibles, haga clic en el botón Exportar situado en la parte superior derecha del menú desplegable de filtros de la barra de herramientas de la pestaña.

Guardar informes de inventario de recursos

Puede guardar un informe con su fecha, servicio y selecciones de filtro, y compartirlo con otros usuarios de la organización concediéndoles permisos de «Solo lectura» o «Edición». En la parte superior derecha de la barra de herramientas de la interfaz de usuario del inventario de recursos, verá un icono con tres puntos elípticos. Al hacer clic en él, se abrirá el menú Acciones del informe con estas opciones.

- **Guardar como informe:** Con esta opción, puede guardar una copia de su informe. Esta opción resulta útil si alguien ha compartido un informe contigo con acceso de «solo lectura» y deseas realizar cambios en dicho informe creando tu propia copia del mismo. Otro caso de uso de Guardar como informe es para el informe predeterminado. El informe predeterminado no se puede modificar y deberá seleccionar la opción «Guardar como informe» para guardar cualquier cambio que haya realizado en el informe predeterminado.
- **Guardar informe:** Esta opción se utiliza para guardar cualquier cambio realizado en el informe que ha creado o que se ha compartido con usted con permiso de «Editar»
- **Compartir informe:** Con esta opción, puede compartir sus informes con otros usuarios de su organización concediéndoles permisos de «Solo lectura» o «Edición».
- **Eliminar informe:** Puede eliminar su informe haciendo clic en Eliminar informe.
- **Gestión del intervalo de fechas de los informes guardados:** Los informes guardados con intervalos de fechas no continuos que no sean compatibles (más de tres meses) se cargarán con el intervalo de fechas restablecido al valor predeterminado de siete días. También se mostrará al usuario un mensaje de aviso indicando que se ha restablecido el intervalo de fechas. Esta función garantiza que se pueda seguir accediendo a los informes guardados incluso cuando los intervalos de fechas en los que están almacenados superen el límite permitido.

Nota:

- El número máximo de informes que se mostrarán en el menú desplegable Informes guardados es 100.
- Cuando se comparte un informe con un usuario, no se enviarán notificaciones por correo electrónico.
- El inventario de recursos admite un máximo de 3 meses de datos, es decir, el mes actual hasta la fecha + los 2 últimos meses. Por lo tanto, los datos caducarían en los informes cuando superaran este periodo de retención.

Uso del inventario de recursos

1. Para acceder al inventario de recursos de OCI, vaya a Insights > Inventario de recursos y haga clic en la pestaña OCI.

1. Seleccione el servicio en el menú desplegable Servicios (actualmente solo Máquina virtual) para el que desea ver su inventario de recursos.
2. Seleccione el intervalo de fechas para el que desea ver los datos del inventario de recursos. Puedes elegir ver hasta un máximo de 31 días de datos. Los datos mostrados se ordenarán por Coste (total) en orden descendente de forma predeterminada.
3. Haga clic en cualquiera de los KPI con la barra azul a la izquierda para filtrar sus informes en función de ese KPI específico.
4. Haga clic en el botón de configuración de la tabla situado en la parte superior derecha de la tabla de inventario de recursos para configurar las medidas y etiquetas que desea que se muestren como columnas en la tabla.

Las medidas y etiquetas seleccionadas se muestran como columnas en la tabla.

1. Haga clic en Filtros para aplicar cualquier filtro a su informe de inventario.
2. Utilice el menú desplegable Mostrar situado encima de la tabla Detalles del inventario de recursos para especificar el porcentaje superior o inferior de filas que se mostrarán en la tabla y para ordenar la tabla de forma descendente según el coste o la métrica de utilización preferidos.
3. Haga clic en el botón Exportar situado en la parte superior derecha de la tabla Detalles del inventario de recursos para exportar todas las columnas que aparecen en la tabla filtradas según su configuración de filtro. Para exportar todos los datos de inventario del mes y servicio seleccionados con todas las columnas compatibles, haga clic en el botón Exportar, situado a la derecha del menú desplegable Filtros en la barra de herramientas de la pestaña.

Medidas de recursos que muestran «No disponible»

En el caso de algunos recursos, es posible que algunas medidas, como Fecha de lanzamiento, Estado y Tamaño, entre otras, aparezcan como No disponible en el informe Inventario de recursos. Esto significa que Cloudability no pudo obtener datos para esas medidas específicas debido a una de las siguientes razones:

- Es posible que no haya realizado la acreditación avanzada para la cuenta a la que pertenecen los recursos específicos.
- Es posible que la vida útil de los recursos haya sido demasiado corta para recopilar los datos necesarios para esas medidas.
- Las métricas de utilización de estos recursos pueden aparecer como «0» (cero) en el informe.

| OCI Compute | |
| --- | --- |
| Total de recursos | Número total de operaciones de lectura de bloques ( VM ) (incluidas instantáneas/copias de seguridad) para el período seleccionado. |
| Total de instancias | Número total de instancias de VM (excluyendo instantáneas/copias de seguridad) para el período seleccionado. |
| Instancias inactivas de VM | Número de instancias de VM que se encuentran en uno de estos estados: «terminating» (terminando), «stopping» (deteniéndose), «stopped» (detenida) o «terminated» (terminada) |
| Coste (total) | Coste total calculado según la tarifa sin combinar |
| Total de instantáneas | Número total de instantáneas (copias de seguridad) de VM para el período seleccionado. |
| Instancias sin etiquetar de « VM » | Número de instancias que no tienen etiquetas. |

**Tema principal:** [Inventario de recursos](../product/resource-inventory.html)
