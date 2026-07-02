---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "AWS S3"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto"
source_path: "product/rightsizing-amazon-s3.html"
images:
  - "images/edit-icon.jpg"
  - "images/s3-rightsizing-details-pane.jpg"
  - "images/s3-rightsizing-recommendations-grid.jpg"
  - "images/s3-storage-classes.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS S3

Puede utilizar el Rightsizing dashboard para ver las recomendaciones de optimización de recursos para Amazon Web Services ( AWS )Simple Storage Service ( S3 ). El cuadro de mandos muestra tanto las recomendaciones de ampliación como las de inactividad (finalización). Puede ver las recomendaciones en varias cuentas desde un único panel de control.

[Redimensionamiento en Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

AWS S3 resumen

Amazon Web Services ( AWS ) S3 es un servicio de almacenamiento organizado en torno a cubos. Los cubos son contenedores de nivel superior. Puede utilizar estos buckets para almacenar objetos individuales que estén asociados a una clase de almacenamiento y también organizar objetos individuales jerárquicamente dentro de carpetas.

Cubos

Puede tener hasta mil cubos por cuenta. Dentro de cada cubo, puede almacenar hasta cinco terabytes de objetos individuales. Los costes se calculan según la tarifa de la clase de almacenamiento del objeto y el factor del espacio de almacenamiento asignado (GB al mes), la duración, el número de operaciones (lectura, escritura, listas, supresión) y el volumen de datos transferidos (salida).

Clases de almacenamiento

Las clases de almacenamiento se adaptan en función de los patrones de acceso y las necesidades de durabilidad, desde el almacenamiento frecuente al poco frecuente (archivo). A una clase de almacenamiento sólo se asocia un objeto, no un cubo.

Las clases de almacenamiento de AWS S3 difieren en precio, rendimiento, disponibilidad y requisitos mínimos de tamaño y duración. Dependiendo de la clase de almacenamiento que utilice, puede incurrir en tasas adicionales por supervisión, transición de clase de almacenamiento, eliminación anticipada y tasas de restauración.

Por defecto, los objetos S3 se crean en la clase de almacenamiento Estándar, que es la más cara. Para optimizar manualmente objetos individuales, es necesario identificar las tarifas de cada clase de almacenamiento por región, recopilar los patrones de acceso y las operaciones anteriores y, a continuación, evaluar cada una de las alternativas teniendo en cuenta todas las compensaciones.

![amazon s3 clases de almacenamiento captura de pantalla](../../../../03-media/cloudability-premium/images/s3-storage-classes.jpg)

Antes de empezar

Para ver el panel de control de AWS S3, asegúrese de haber conectado Cloudability a las cuentas correctas de AWS.

[Conexión con AWS - Guía de integración de clientes](../admin/aws-credentialing-standard-enterprise-home.html)

Acceda al panel de control de AWS S3.

Para acceder al panel de control de AWS EC2, abra la página de inicio de Cloudability y, en el menú de navegación de la izquierda, seleccione Optimizar > Redimensionar. En la página Rightsizing, seleccione la pestaña AWS y, a continuación, seleccione la subpestaña S3.

Nota:

Sólo se mostrarán los cubos con costes incurridos superiores a cero.

![Captura de pantalla de AWS Rightsizing](../../../../03-media/cloudability-premium/images/s3-rightsizing-recommendations-grid.jpg)

Cada día, Cloudability analiza las métricas de coste, uso y utilización de AWS S3 durante los últimos 30 días. El redimensionamiento produce información a nivel de cubo y recomendaciones de optimización. El gasto se determina por meses GB.

Nota: El Rightsizing proporciona una separación de clases de almacenamiento heterogéneas dentro de un bucket.

Nota: Los recursos inactivos o los volúmenes de almacenamiento asignados que contienen datos insignificantes o inexistentes también se muestran en el panel de Rightsizing.

Personalizar el salpicadero

Puedes configurar las siguientes opciones para personalizar tu panel de control.

Nota:

Sólo se admite la base de costes a la carta para S3.

La base de costos bajo demanda proporciona una comparación directa entre la instancia que aparece en la columna Actual y la instancia recomendada en la columna Nueva basándose únicamente en el precio bajo demanda. No incluye ningún impacto potencial de las Instancias Reservadas (IR) ni de los Planes de Ahorro (PA). Tenga en cuenta que los precios a la carta reflejarán cualquier acuerdo de precios personalizado que haya configurado en Cloudability.

Seleccionar cuenta

Por defecto, el panel muestra recomendaciones para todas las cuentas. Para ver las recomendaciones de una cuenta concreta, seleccione el nombre de la cuenta en el desplegable Cuenta.

Especifique el plazo

Puede elegir entre revisar los gastos de los últimos 10 días o de los últimos 30 días. Por defecto, la opción Plazo está fijada en 10 días. Para la mayoría de los usuarios, 10 días es el periodo de tiempo recomendado porque captura las tendencias de rendimiento más recientes y es más predictivo del uso futuro de los recursos.

Aplicar filtros

Puede añadir filtros para incluir o excluir datos en función de una o varias condiciones.

Añadir un filtro

Para añadir un filtro:

1. Seleccione Añadir filtro en la barra de herramientas.
2. En el menú Añadir filtro, elija una dimensión.
3. Seleccione un Operador para proporcionar una condición lógica.
4. Elija un valor para afinar el filtro.
5. Seleccione Añadir filtro para aplicar el nuevo filtro a la página.

Aplicar filtros con enlaces

También puede añadir filtros seleccionando los valores hipervinculados en azul en la tabla principal. La regla de filtrado se aplica automáticamente al campo Filtros. Sólo puede seleccionar un valor o parámetro de cada columna a la vez.

Eliminar un filtro

Para quitar un filtro:

1. Seleccione el icono de filtro ![icono de edición](../../../../03-media/cloudability-premium/images/edit-icon.jpg) .
2. Seleccione X junto al filtro que desea eliminar.

Indicadores clave de rendimiento

Puede ver los siguientes Indicadores Clave de Rendimiento (KPI) en su panel de Rightsizing:

- Total de gastos : Muestra el total de gastos asignados actuales.
- Ahorro estimado de Rightsize : Muestra el ahorro potencial total estimado que se puede conseguir con todas las recomendaciones de Rightsize.
- Gasto optimizado estimado : Muestra el gasto total estimado después de aplicar las recomendaciones.

Tabla de recomendaciones de redimensionamiento

El cuadro de mandos contiene una tabla de recomendaciones de dimensionamiento, que ofrece una visión general de sus recursos S3. La tabla incluye las siguientes columnas:

Nota:

Por defecto, los datos se ordenan por la columna Ahorro de costes. Para cambiar el orden de clasificación, sólo tiene que seleccionar el nombre de la columna.

- Nombre del cubo : El nombre del cubo de S3.
- Nombre de cuenta : El nombre de la cuenta AWS.
- Tamaño : El tamaño de todos los objetos dentro del cubo.
- Objetos : El número de objetos dentro del cubo.
- Peticiones : El número de peticiones (lectura, escritura, lista) realizadas a través de la consola o la API.
- Coste : El coste incurrido en los últimos 30 días para los objetos dentro del cubo.
- Actual : La clase de almacenamiento derivada para el cubo. Cuando el 100% de todos los objetos estén en la misma clase de almacenamiento, se mostrará esa clase de almacenamiento. Si un bucket está formado por objetos de varias clases de almacenamiento, se mostrará MIXTO. Al hacer clic en los detalles se mostrará la distribución relativa entre estas clases.
- Nuevo : La clase de almacenamiento óptima recomendada para todos los objetos dentro del cubo.
- Acción : Recomendación para el recurso. La recomendación puede ser una de las siguientes

| Recomendación | Descripción |
| --- | --- |
| Dimensionar correctamente | Cambia el tamaño al tipo de recurso especificado en la columna Nuevo. |
| Ninguna acción | Por defecto no se recomienda ninguna acción, pero en el panel de detalles puede haber recomendaciones adicionales con niveles de riesgo más altos. |

Ahorro de costes : Importe estimado del ahorro de costes a 10 o 30 días.

Exportar recomendaciones a un archivo Excel

Para exportar las recomendaciones a un archivo Excel, seleccione Exportar. Tenga en cuenta que el archivo Excel incluirá varias columnas adicionales, como región, sistema operativo, precio unitario y otros.

Detalles de la recomendación

Para ver los detalles de la recomendación de un recurso concreto, seleccione Ver detalles en el menú Más opciones (3 puntos).

La siguiente figura muestra un panel de detalles de la recomendación.

![detalles de la recomendación](../../../../03-media/cloudability-premium/images/s3-rightsizing-details-pane.jpg)

El panel de detalles de S3 muestra la siguiente información:

Recomendaciones

Muestra una o varias recomendaciones, clasificadas por ahorro de costes y riesgo (0-5).

- Ahorro: Porcentaje de ahorro estimado para el periodo de 10 ó 30 días.
- Ahorro de costes : Importe estimado del ahorro.
- Clase de almacenamiento : Clase de almacenamiento recomendada.
- Acción : Acción recomendada.
- Riesgo : En una escala de 0 a 5, el número de transiciones de clase de almacenamiento de acceso frecuente a infrecuente.

Gráficos

- Tamaño de almacenamiento (Bytes) : Muestra la cantidad de tamaño de almacenamiento por clase de almacenamiento. Los valores posibles son los siguientes:
  - Standard
  - FA inteligente (clasificación inteligente por niveles - acceso frecuente)
  - IA Inteligente (Nivelación Inteligente = Acceso Poco Frecuente)
  - Acceso poco frecuente
  - Una zona
  - Glacier
  - Archivo profundo
  - Redundancia reducida
- Peticiones (Lectura/Escritura/Cuento) : Muestra las peticiones de lectura y escritura realizadas contra el cubo. Este gráfico proporciona información valiosa sobre la categoría de uso del bucket, como lectura mayoritaria, lectura-escritura equilibrada u orientada a la escritura.
- Número de objetos (recuento) : El gráfico muestra el número de objetos en el cubo durante el periodo de tiempo.
- Datos transferidos (Bytes) : Cantidad de salida a Internet (o datos transferidos entre regiones).
- Transiciones de datos (Bytes) : Cantidad de datos que pasan de una clase de almacenamiento a otra (excluida la estándar).
- Borrado anticipado (Bytes) : Cantidad de almacenamiento que incurre en una tasa de borrado anticipado.

Seguimiento de las recomendaciones

Clases de almacenamiento

Para cambiar la clase de almacenamiento de los objetos en bloque, tiene dos opciones:

- Gestión del ciclo de vida de los objetos

  Puede activar una regla de gestión del ciclo de vida a nivel de bucket para que todos los objetos contenidos pasen a la clase de almacenamiento recomendada en función de la fecha de creación del objeto.

  Para obtener más información sobre la gestión del ciclo de vida de los objetos, consulta «[Gestión del ciclo de vida de los objetos](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html "(se abre en una pestaña o una ventana nueva)") ».
- S3 Operaciones por lotes

  Si prefiere una ruta programática, puede aprovechar S3 Batch Operations para cambiar la clase de almacenamiento de todos los objetos o de los seleccionados dentro de uno o varios buckets.

  Para más información sobre las operaciones por lotes, consulte [https://aws.amazon.com/blogs/aws/new-amazon-s3-batch-operations/](https://aws.amazon.com/blogs/aws/new-amazon-s3-batch-operations/ "(se abre en una pestaña o una ventana nueva)").

Clasificación inteligente por niveles

Intelligent Tiering es un servicio de clase de almacenamiento híbrido que supervisa los patrones de acceso y los atributos de cada objeto. Basándose en estos datos, el servicio realizará automáticamente la transición de objetos entre la clase de almacenamiento Estándar y Acceso Poco Frecuente por una tarifa de supervisión por objeto, además de las tarifas específicas de la clase de almacenamiento.

La redimensión a nivel de cubo le ayuda a identificar qué cubos se beneficiarán de este servicio. Aunque la mayoría de los objetos se crean inicialmente en la clase Estándar, a medida que sus cubos de S3 se optimizan con el tiempo, pueden recomendarse recomendaciones de optimización incremental adicionales, como Acceso poco frecuente o incluso Glacier.

Para más información, consulte [https://aws.amazon.com/s3/storage-classes/](https://aws.amazon.com/s3/storage-classes/ "(se abre en una pestaña o una ventana nueva)").

**Tema principal:** [Redimensionamiento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
