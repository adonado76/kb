---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "AWS Lambda"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto"
source_path: "product/rightsizing-aws-lambda.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS Lambda

Utilice el Rightsizing dashboard para ver las recomendaciones de optimización de recursos para Amazon Web Services ( AWS ) Lambda. El cuadro de mandos muestra tanto las recomendaciones de ampliación como las de inactividad (finalización). Puede ver las recomendaciones en varias cuentas desde un único panel de control.

Visite [Rightsizing en Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html) para obtener más información.

## Antes de empezar

- Habilite los permisos correctos, que son:
  - lambda:ListFunctions
  - lambda:ListProvisionedConcurrencyConfigs
- Active la supervisión mejorada de Lambda Insights. Esto permite a Cloudability recuperar métricas de memoria para sus funciones Lambda.
- Conecte Cloudability a sus cuentas correctas de AWS.
- Para los clientes que ya dispongan de conexiones con cuentas de AWS : Crea o descarga una plantilla de credenciales actualizada de AWS en Cloudability y sube la nueva plantilla de credenciales a la consola de gestión de AWS.
- Visite las siguientes páginas para obtener más información:
  - [Activación de Lambda Insights](https://docs.aws.amazon.com/lambda/latest/dg/monitoring-insights.html "(se abre en una pestaña o una ventana nueva)")
  - [Conectar Amazon Web Services](../admin/aws-credentialing-standard-enterprise-home.html)

## Explora el panel de control « AWS Lambda » (Aprendizaje de la vida cotidiana)

El panel contiene una tabla de recomendaciones de dimensionamiento, que proporciona una visión general de sus recursos Lambda. La tabla incluye las siguientes columnas:

- ID del recurso : ID de la función.
- Nombre del recurso : El nombre de la función.
- Nombre de cuenta : El nombre de la cuenta AWS.
- Última ejecución : La fecha en que la función se ejecutó por última vez.
- Coste : El coste total de la función.
- Memoria actual : La cantidad de memoria configurada actualmente.
- Memoria nueva : La memoria configurada más recomendada.
- Ahorro de costes : El importe del ahorro de costes identificado.
- Acción : Recomendación para el recurso. La recomendación puede ser una de las siguientes

| Recomendación | Descripción |
| --- | --- |
| Dimensionar correctamente | Redimensiona al tipo de recurso especificado en la columna Nueva memoria. |
| Terminar | Dar de baja su recurso porque está predominantemente ocioso. |
| Ninguna acción | No se recomienda ninguna acción por defecto.. Sin embargo, en el panel de Detalles puede haber recomendaciones adicionales con niveles de riesgo más elevados. |

Nota: Por defecto, los datos se ordenan por la columna Ahorro de costes. Para cambiar el orden de clasificación, seleccione el nombre de la columna.

## Acceda al panel de control de AWS Lambda

Para acceder al panel de control « AWS Lambda »:

1. Abrir Cloudability. En el menú de navegación, seleccione Optimizar > Redimensionar.
2. Seleccione la pestaña AWS y, a continuación, seleccione la subpestaña Lambda.

## Personalizar el salpicadero

Nota: Sólo se admite la base de costes bajo demanda para Lambda. La base de costos bajo demanda proporciona una comparación directa entre la memoria que aparece en la columna Memoria actual y la memoria recomendada en la columna Memoria nueva, basándose únicamente en los precios bajo demanda. No incluye ningún impacto potencial de las Instancias Reservadas (IR) ni de los Planes de Ahorro (PA). Tenga en cuenta que los precios a la carta reflejarán cualquier acuerdo de precios personalizado que haya configurado en Cloudability.

Puedes configurar las siguientes opciones para personalizar tu panel de control:

1. Seleccione Cuenta : Por defecto, el panel muestra recomendaciones para todas las cuentas. Para ver las recomendaciones de una cuenta concreta, seleccione el nombre de la cuenta en el menú desplegable Seleccionar cuenta.
2. Especificar plazo : Puede elegir revisar los gastos de los últimos 10 días o de los últimos 30 días. Por defecto, la opción Plazo está fijada en 10 días. Para la mayoría de los usuarios, 10 días es el periodo de tiempo recomendado porque captura las tendencias de rendimiento más recientes y es más predictivo del uso futuro de los recursos.
3. Aplicar filtros : Puedes añadir filtros para incluir o excluir datos en función de una o varias condiciones.

## Añadir filtros con la opción de filtro

Para añadir un filtro:

1. Seleccione Añadir filtro en la barra de herramientas.
2. En el menú Añadir filtro, elija una dimensión.
3. Seleccione un Operador para proporcionar una condición lógica.
4. Elija un valor para afinar el filtro.
5. Seleccione Añadir filtro para aplicar el nuevo filtro a la página.

## Aplicar filtros con enlaces

También puede añadir filtros seleccionando los valores hipervinculados en azul en la tabla principal. La regla de filtrado se aplica automáticamente al campo Filtros. Sólo puede seleccionar un valor o parámetro de cada columna a la vez.

## Ver detalles de la recomendación

Para ver los detalles de la recomendación de un recurso concreto, seleccione el menú Más opciones (3 puntos) y seleccione Ver detalles.

- Para ver descripciones de las dimensiones y métricas de costos, visite [Glosario de dimensiones y métricas de costos](glossary-of-cost-dimensions-and-metrics.html).
- Para ver detalles de la dimensión y métricas de utilización, visite el [Glosario de dimensiones y métricas de utilización](glossary-of-utilization-dimensions-and-metrics.html).

**Tema principal:** [Redimensionamiento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
