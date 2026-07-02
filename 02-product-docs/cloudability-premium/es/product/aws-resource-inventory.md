---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "AWS Inventario de recursos"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
  - "Inventario de recursos"
source_path: "product/aws-resource-inventory.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS Inventario de recursos

AWS La función Inventario de recursos de Cloudability le permite generar una lista oficial de los recursos en la nube de AWS que existían y se facturaron durante un período de informe específico. Tienes la flexibilidad de crear esta lista a partir de recursos que abarcan varias cuentas y elegir entre diferentes medidas (dimensiones y métricas) para mostrar los detalles relevantes para ellas. Esta información, disponible para cada recurso en la nube, unifica la facturación, la utilización y los metadatos descriptivos para ofrecerle una visión más completa del inventario.

## cómo empezar

AWS La función de informes de inventario de recursos debe estar activada en su organización Cloudability. Para ello, debes ponerte en contacto con tu TAM/CSM/punto de contacto de Apptio. Una vez activado, espere 2-3 días laborables para que los datos empiecen a aparecer en sus informes de inventario. Para obtener los datos completos del inventario de AWS Lambda, debe habilitar **Lambda Insights** en su consola de AWS.

## Medidas de información sobre el inventario

- Las medidas se clasifican en columnas generales o columnas de etiquetas. Puede incluir hasta 20 columnas en un informe individual.
- Para cada servicio de AWS se admite un conjunto específico de medidas.
- Puede filtrar sus respectivos informes de inventario utilizando cualquiera de las medidas disponibles en esta función.

## Indicadores clave de rendimiento en los que se puede hacer clic para filtrarlos rápidamente

Para cada servicio (Por ejemplo: EC2, EBS ), los KPIs se mostrarán en la parte superior del informe para proporcionarle información resumida clave como Instancias Inactivas e Instancias No Etiquetadas. Puede hacer clic y filtrar el informe Inventario en función de estos KPI para desglosar los datos específicos del informe que está buscando.

## Ventanas de fecha de informe de inventario

- Seleccione el periodo en el selector de fechas para ver los datos de inventario de cada servicio.

  El intervalo máximo permitido para la selección es de 31 días.

  Los datos del inventario de recursos se retrotraen al principio del mes en curso y están disponibles en una ventana móvil de tres meses.
- Acceda a los datos de inventario de recursos del mes en curso junto con los de los dos meses anteriores siempre que lo necesite.

## Filtrado estadístico mediante el filtro de visualización

A partir de los datos de inventario generados para un servicio y un periodo de tiempo específicos, puede optar por mostrar un subconjunto de esos datos, ya sea el número x superior o el porcentaje x de recursos en función de la métrica de coste o utilización que prefiera.

Por ejemplo: Inventario de recursos muestra 1000 registros para el servicio EC2 para un periodo de siete días. Puede filtrar aún más esta visualización eligiendo ver sólo el 25% superior de estos recursos, basándose en el Coste (Total). Aplicando este filtro se obtendrían los 250 recursos más importantes en función de su coste (total), ordenados de mayor a menor.

## Exportación de informes

Haga clic en Exportar en la cuadrícula del informe para exportar las columnas de inventario seleccionadas con filtro(s) aplicado(s). Sin embargo, para exportar los datos de inventario completos del mes y servicio seleccionados para todas las columnas admitidas, haga clic en el botón Exportar, a la derecha del desplegable Filtros de la barra de herramientas de la pestaña.

## Guardar informes de inventario de recursos

Puede guardar un informe con sus selecciones de fecha, servicio y filtro y compartirlo con otros usuarios de la organización concediéndoles permisos de "Sólo ver" o "Editar". En la parte superior derecha de la barra de herramientas de la interfaz de usuario del inventario de recursos, puede ver una elipse con un icono de tres puntos en el que al hacer clic se abrirá el menú Acciones del informe con estas opciones.

- **Guardar como informe:** Con esta opción puede guardar una copia de su informe. Esta opción es útil si alguien ha compartido un informe con usted con un acceso de "Sólo Ver" y usted quiere hacer cambios en este informe haciendo su propia copia del mismo. Otro caso de uso de Guardar como informe es para el Informe por defecto. El informe por defecto no puede modificarse, por lo que deberá seleccionar la opción "Guardar como informe" para guardar los cambios realizados en el informe por defecto.
- **Guardar informe:** Esta opción se utiliza para guardar cualquier cambio realizado en el informe creado o compartido con usted con un permiso "Editar"
- **Compartir informe:** Utilizando esta opción, puedes compartir tus informes con otros usuarios de tu organización dándoles permisos de "Sólo ver" o "Editar".
- **Borrar informe:** Puede eliminar su informe haciendo clic en Eliminar informe.
- **Gestión del intervalo de fechas de los informes guardados:** Los informes guardados con intervalos de fechas no continuos que no sean compatibles (superiores a tres meses) se cargarán con el intervalo de fechas restablecido a los 7 días predeterminados. También se mostrará al usuario un mensaje de aviso indicando que se ha restablecido el intervalo de fechas. Esta función garantiza que se pueda seguir accediendo a los informes guardados incluso cuando los intervalos de fechas en los que están almacenados superen el límite permitido.

Nota:

- El número máximo de informes que se mostrarán en el desplegable Informes guardados es 100.
- Cuando se comparta un informe con un usuario, no se enviarán notificaciones por correo electrónico.
- El inventario de recursos admite un máximo de 3 meses de datos, es decir, el mes hasta la fecha + los 2 últimos meses. Así, los datos acabarían caducando en los informes cuando superasen este periodo de conservación.

## Utilización del inventario de recursos

1. Para acceder a AWS Inventario de recursos, vaya a Insights > Inventario de recursos.
2. Seleccione en el menú desplegable Servicios el servicio cuyo inventario de recursos desea consultar.
3. Seleccione el intervalo de fechas para el que desea ver los datos del inventario de recursos. Puedes elegir ver hasta 31 días de datos como máximo. Por defecto, los datos mostrados se ordenan por Coste (Total) en orden descendente.
4. Haga clic en los KPI con una barra azul a la izquierda para filtrar sus informes en función de ella (por ejemplo, Recién lanzados ).
5. Haga clic en Configuración de la tabla en la parte superior derecha de la tabla Detalles del inventario de recursos para configurar las medidas y etiquetas que desea que se muestren como columnas en la tabla.
6. Haga clic en Filtros para ordenar el informe de inventario.
7. Seleccione Mostrar encima de la tabla Detalles del inventario de recursos. Especifica el porcentaje superior o inferior de filas que se mostrarán en la tabla y también ordena la tabla por la métrica de coste o utilización preferida en orden descendente.
8. Haga clic en Exportar para exportar las columnas mostradas en la tabla, filtradas según sus ajustes de filtro. Para exportar todos los datos de inventario del mes y servicio seleccionados con las columnas admitidas, haga clic en el botón Exportar situado a la derecha del desplegable de filtros en la barra de herramientas de la pestaña.

Nota:

Los recursos, como la fecha de lanzamiento, el estado y el tamaño, a veces aparecen como No disponibles en el informe Inventario de recursos. Esto significa que Cloudability no pudo obtener datos para esas medidas específicas debido a una de las siguientes razones:

- Es posible que no haya realizado credenciales avanzadas para la cuenta a la que pertenecen los recursos concretos.
- La vida útil de los recursos puede haber sido demasiado corta para recoger los datos de esas medidas.
- Las métricas de utilización de estos recursos pueden aparecer como "0" (cero) en el informe.

Nota:

Las métricas de utilización de estos recursos pueden aparecer como "0" (cero) en el informe.

## Utilización Familia de recursos en el inventario de recursos

El inventario de recursos utiliza el ID de recurso como identificador único para mostrar los recursos. A diferencia de los informes de Cloudability, no admite las dimensiones de la familia de uso. Aunque el mismo ID de recurso se consuma en diferentes familias de uso, el inventario de recursos sólo mostrará el ID de recurso una vez en el informe.

## Definiciones de KPI

| ICR | Descripción |
| --- | --- |
| EC2 | |
| Número total de instancias | Número total de instancias de EC2 en su inventario para el periodo seleccionado. |
| Instancias recién lanzadas | Número de instancias de EC2 que se lanzaron en el periodo seleccionado. |
| Instancias inactivas | Número de instancias de EC2 que no están en estado "En ejecución". |
| Coste (total) | Coste (Total) de las instancias de EC2 para el periodo seleccionado. |
| Instancias no etiquetadas | Número de instancias de EC2 que no tienen etiqueta. |
| EBS | |
| Total de recursos | Número total de recursos EBS en su inventario para el periodo seleccionado. |
| Total de instantáneas | Número total de instantáneas EBS en su inventario para el periodo seleccionado. |
| Creación de nuevos volúmenes | Número de volúmenes EBS que se crearon en el periodo seleccionado. |
| Volúmenes desocupados | Número de volúmenes de EBS que están en estado "Disponible". |
| Coste (total) | Coste (Total) de los recursos EBS (tanto volúmenes como instantáneas). |
| Volúmenes no etiquetados | Número de volúmenes de EBS que no tienen etiqueta. |
| Volúmenes desconectados | Número de volúmenes de EBS que no están adjuntos a ninguna instancia de EC2. |
| Lambda | |
| Total de funciones lambda | Número total de funciones Lambda en su inventario para el periodo seleccionado. |
| Calcular funciones lambda | Número de Lambda Functions para el periodo seleccionado que entran dentro de la familia de uso "Instance Usage" |
| Coste (total) | Coste (Total) de las Funciones Lambda para el periodo seleccionado. |
| Funciones no etiquetadas | Número de funciones lambda que no tienen etiqueta. |
| S3 | |
| Total de recursos | Número total de cubos S3 en su inventario para el periodo seleccionado. |
| Grupos desocupados | Número de cubos de S3 que no contienen ningún objeto. |
| Grupos no etiquetados | Número de cubos de S3 que no tienen etiqueta |
| Coste (total) | Coste (total) de los cubos S3. |
| RDS | |
| Total de recursos | Número total de recursos RDS en su inventario para el periodo seleccionado. |
| Total de instantáneas | Número total de instantáneas RDS en su inventario para el periodo seleccionado. |
| Recursos no etiquetados | Número de recursos RDS que no tienen etiqueta |
| Coste (total) | Coste (total) de los recursos RDS. |
| Redshift | |
| Total de recursos | Número total de recursos « Redshift » en su inventario para el período seleccionado. |
| Total de instantáneas | Número total de instantáneas de Redshift en su inventario para el período seleccionado. |
| Creación de nuevos recursos | Número de recursos de Redshift creados en el período seleccionado. |
| Recursos no etiquetados | Número de recursos Redshift que no tienen etiqueta. |
| Coste (total) | Coste (total) de los recursos « Redshift ». |

**Tema principal:** [Inventario de recursos](../product/resource-inventory.html)
