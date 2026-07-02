---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "AWS ElasticIP"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto"
source_path: "product/aws_elasticip.html"
images:
  - "images/edit-icon.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS ElasticIP

Puedes utilizar las recomendaciones de Cloudability para identificar direcciones Amazon Web Services ( AWS ) ElasticIP que no estén asociadas a ningún dominio. El panel de control ofrece recomendaciones para eliminar las direcciones ElasticIP que se ha determinado que no están asociadas a ninguna instancia y que no se utilizan. Puedes consultar las recomendaciones de varias cuentas desde un único panel de control.

[Ajuste de plantilla en Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

## Antes de empezar

Para ver el panel de control de « AWS EC2 » ( EBS ), asegúrate de haber vinculado Cloudability a las cuentas correctas de AWS.

[Conexión con AWS - Guía de integración para clientes](../admin/aws-credentialing-standard-enterprise-home.dita "(se abre en una pestaña o una ventana nueva)")

## Acceso a AWS : Recomendaciones sobre direcciones IP elásticas

Para acceder al panel de control de « AWS EC2 » ( EBS ), abre la página de inicio de Cloudability y, en el menú de navegación de la izquierda, **selecciona** «Optimizar» > «**Rightsizing** ». En **la** página «Rightsizing», selecciona la pestaña « **AWS** » y, a continuación, selecciona **la** subpestaña «Elastic IP».

## Cómo interpretar tus recomendaciones

Nota: Para las direcciones de « ElasticIP » solo se admite la base de coste «On-Demand».

La base de coste «On-Demand» ofrece una comparación directa entre la instancia que aparece en **la** columna «Actual» y la instancia recomendada en **la** columna «Nueva», basándose exclusivamente **en** **la tarifa «On-Demand** ». Dado que las direcciones de « ElasticIP » no admiten compromisos, solo está disponible la base de coste «On Demand», que no incluye ningún posible impacto derivado de las instancias reservadas (RI) ni de los planes de ahorro (SP). Ten en cuenta que los precios bajo demanda reflejarán cualquier acuerdo de precios personalizados que hayas configurado en Cloudability.

**Seleccionar cuenta**

Por defecto, el panel de control muestra recomendaciones para todas las cuentas. Para ver las recomendaciones de una cuenta concreta, selecciona el nombre de la cuenta en el menú desplegable «Cuenta».

**Especificar el calendario**

Puedes elegir entre consultar el gasto de los últimos **10 días** o el de los últimos 30 días. Por defecto, **la** opción «Línea de tiempo» está configurada en 10 días. A modo de recomendación sobre los « ElasticIP » inactivos, se aconseja dar de baja el recurso si ha permanecido sin asignar durante, al menos, la última mitad del periodo de análisis retrospectivo.

**Aplicar filtros**

Puedes añadir filtros para incluir o excluir datos en función de una o varias condiciones.

**Añadir un filtro**

Para añadir un filtro:

1. **Sel** ecciona «Añadir filtro» en la barra de herramientas.
2. En **el** menú «Añadir filtro», selecciona **una** «Dimensión».
3. Selecciona un **operador** para establecer una condición lógica.
4. Elige un valor para afinar el filtro.
5. **Sel** ecciona «Añadir filtro» para aplicar el nuevo filtro a la página.

**Aplicar filtros con enlaces**

También puedes añadir filtros seleccionando los valores con hipervínculo azul de la tabla principal. La regla de filtrado se aplica automáticamente al **campo** «Filtros». Solo puedes seleccionar un valor o parámetro de cada columna cada vez.

**Eliminar un filtro**

Para eliminar un filtro:

1. Selecciona el icono del filtro. ![](../../../../03-media/cloudability-premium/images/edit-icon.jpg)
2. Selecciona la «X» situada junto al filtro que quieras eliminar.

## Indicadores clave de rendimiento

En tu panel de control de Rightsizing puedes consultar los siguientes indicadores clave de rendimiento (KPI):

- **Total** **Spend** : muestra el gasto total actual en los recursos de ElasticIP, junto con recomendaciones
- **A** **horro estimado por inactividad** : muestra el ahorro total estimado para todas las recomendaciones de «Terminate».
- **A** **horro estimado por el programa Rightsize** : Muestra el ahorro total potencial estimado que se puede conseguir con todas las recomendaciones de Rightsize. Dado que las direcciones IP elásticas solo admiten recomendaciones de terminación, es de esperar que este valor sea 0.
- **G** **asto optimizado estimado** : muestra el gasto total estimado tras aplicar las recomendaciones. Dado que las direcciones IP elásticas solo admiten recomendaciones de terminación, es de esperar que este valor sea 0.

## Tabla de recomendaciones para la optimización de la plantilla

El panel de control incluye una tabla con recomendaciones sobre el ajuste de recursos, que ofrece una visión general de los recursos de AWS ElasticIP. La tabla incluye las siguientes columnas:

Nota: Por defecto, los datos se ordenan según la columna «Ahorro de costes». Para cambiar el orden de clasificación, solo tienes que seleccionar el nombre de la columna.

- **Res** **ourceID** : El identificador del volumen.
- **Res** **ourceName** : El nombre del volumen.
- **N** **ombre de la cuenta** : El nombre de la cuenta de AWS.
- **Inactivo** : El porcentaje de horas con cero IOPS.
- **Estado** : El estado puede ser «Adjunto», «No adjunto» o «Eliminado».
- **Coste** : El coste total del volumen.
- **Tipo** : El tipo de volumen.
- **Tamaño** : El volumen ( GiB ).
- **New** **Type** : el tipo de volumen más recomendado.
- **New** **Type** : el tipo de volumen más recomendado.
- **New** **Size** : El tamaño de volumen más recomendado (en « GiB »).
- **Acción** : Recomendación sobre el recurso; actualmente solo hay disponibles recomendaciones de cancelación para las direcciones ElasticIP.

**A** **horro de costes** : Importe estimado del ahorro de costes a 10 o 30 días.

**Exportar recomendaciones a un archivo de Excel**

Para exportar las recomendaciones a un archivo de Excel, selecciona «Exportar». Ten en cuenta que el archivo de Excel incluirá varias columnas adicionales, como la región, el sistema operativo, el precio unitario y otras.

**Detalles de la recomendación**

Para ver los detalles de la recomendación de un recurso concreto, selecciona «Ver detalles» en el menú «Más opciones» (tres puntos).

El panel de detalles de « EBS » muestra la siguiente información:

- **Última** **fecha de facturación** : La última fecha para la que se dispone de datos sobre los costes.
- **Última** **fecha de conexión** : La última fecha en la que se conectó el volumen.
- **Último** **ID de** instancia conectada: el ID de la última instancia a la que se conectó el volumen.
- **Tipo** : El tipo de volumen.
- **T** amaño: El volumen.
- **Capacidad de procesamiento** : El volumen máximo de procesamiento.
- **IOPS** : el volumen máximo de IOPS.
- **Riesgo (según las recomendaciones)** : Caracteriza la probabilidad de alcanzar los límites de capacidad para una recomendación determinada.
- **M** **étricas de utilización** : Las métricas de utilización que se muestran para los volúmenes de « EBS » se basan en los siguientes parámetros.

**Tema principal:** [Redimensionamiento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
