---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "GCP Google Cloud Storage (GCS)"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto"
source_path: "product/rightsizing-for-gcp-cloud-storage.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# GCP Google Cloud Storage (GCS)

Puede utilizar el panel de control de Rightsizing para ver las recomendaciones de optimización de recursos para el Servicio de Almacenamiento en la Nube de Google ( Google Cloud Storage, GCS). El panel de control muestra tanto las recomendaciones de ajuste de tamaño como las de inactividad (cierre). Puedes consultar las recomendaciones de varias cuentas desde un único panel de control.

[Reducción de plantilla en Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Google Cloud Storage resumen

Google Cloud Storage (GCS) es un servicio de almacenamiento organizado en buckets. Los buckets son contenedores de primer nivel. Puedes utilizar estos buckets para almacenar objetos individuales asociados a una clase de almacenamiento y también para organizar dichos objetos jerárquicamente en carpetas.

Cubos

En cada depósito, puedes almacenar un número ilimitado de objetos individuales. Los costes se calculan según la tarifa correspondiente a la clase de almacenamiento del objeto y se multiplican por el espacio de almacenamiento asignado (GB al mes), el número de operaciones (lectura, escritura, listado), las operaciones de recuperación (para Nearline, Coldline y Archive) y el volumen de datos transferidos (salida).

Clases de almacenamiento

Las clases de almacenamiento se adaptan en función de los patrones de acceso y las necesidades de durabilidad, y abarcan desde el almacenamiento frecuente hasta el poco frecuente (de archivo). Solo un objeto, y no un contenedor, está asociado a una clase de almacenamiento.

Las clases de almacenamiento de GCS difieren en cuanto a precio, rendimiento, disponibilidad y requisitos de duración mínima de almacenamiento. Dependiendo de la clase de almacenamiento que utilices, pueden aplicarse tarifas adicionales por las operaciones de recuperación (acceso a datos de las clases Nearline, Coldline o Archive).

De forma predeterminada, los objetos de GCS se crean en la clase de almacenamiento «Standard». Para optimizar manualmente objetos concretos, es necesario determinar las tasas de cada clase de almacenamiento por ubicación, recopilar los patrones de acceso y las operaciones anteriores y, a continuación, evaluar cada una de las alternativas teniendo en cuenta todas las ventajas e inconvenientes.

Antes de empezar

Para ver el panel de control de GCS, asegúrate de haber vinculado Cloudability a las cuentas de GCP correctas y de haber activado la facturación por recursos (RLB).

Nota:

Para las recomendaciones de optimización de recursos de GCS es necesario el sistema de facturación detallada (también conocido como facturación a nivel de recursos). Para obtener información sobre cómo habilitar la facturación detallada en la configuración de GCP, consulta «[Conéctate con Google Cloud](../admin/connect-google-cloud.html) ».

Accede al panel de control de « Google Cloud Storage »

Para acceder al panel de control de GCS, abre la página de inicio de Cloudability y, en el menú de navegación de la izquierda, selecciona «Optimizar > Ajustar el tamaño ». En la página «Rightsizing», seleccione la pestaña « GCP » y, a continuación, seleccione la subpestaña «GCS ».

Nota:

Solo se mostrarán los grupos con costes incurridos superiores a cero.

Cada día, Cloudability analiza tus métricas de costes, consumo y utilización de GCS correspondientes a los últimos 30 días. Rightsizing ofrece información detallada a nivel de cubo y recomendaciones de optimización. El gasto se calcula en función de los meses de GB.

Nota: Los recursos inactivos o los volúmenes de almacenamiento asignados que contienen datos insignificantes o ninguno también se muestran en el panel de control de Rightsizing.

Personalizar el panel de control

Puedes configurar las siguientes opciones para personalizar tu panel de control.

Seleccionar cuenta

Por defecto, el panel muestra recomendaciones para todas las cuentas. Para ver las recomendaciones de una cuenta concreta, selecciona el nombre de la cuenta en el menú desplegable «Cuenta ».

Aplicar filtros

Puedes añadir filtros para incluir o excluir datos en función de una o varias condiciones.

Añadir un filtro

Para añadir un filtro:

1. Selecciona «Añadir filtro» en la barra de herramientas.
2. En el menú «Añadir filtro», selecciona una dimensión.
3. Selecciona un operador para establecer una condición lógica.
4. Elige un valor para refinar el filtro.
5. Selecciona «Añadir filtro» para aplicar el nuevo filtro a la página.

Aplicar filtros con enlaces

También puedes añadir filtros seleccionando los valores con hipervínculos azules de la tabla principal. La regla de filtrado se aplica automáticamente al campo «Filtros ». Solo puedes seleccionar un valor o parámetro de cada columna a la vez.

Eliminar un filtro

Para eliminar un filtro: selecciona la «X» situada junto al filtro que deseas eliminar.

Tabla de recomendaciones para la optimización de la plantilla

El panel de control incluye una tabla de recomendaciones de ajuste de recursos, que ofrece una visión general de tus recursos de GCS. La tabla incluye las siguientes columnas:

Nota:

Por defecto, los datos se ordenan según la columna «Ahorro de costes ». Para cambiar el orden de clasificación, solo tienes que seleccionar el nombre de la columna.

- Nombre del depósito : El nombre del depósito de GCS.
- Nombre de la cuenta : El nombre de la cuenta de GCP.
- Tamaño : El tamaño de todos los objetos contenidos en el depósito.
- Objetos : el número de objetos que hay dentro del cubo.
- Solicitudes : el número de solicitudes (lectura, escritura, listado) realizadas a través de la consola o la API.
- Coste : el coste incurrido durante los últimos 30 días por los objetos incluidos en el bucket.
- Actual : La clase de almacenamiento derivada para el bucket. Cuando el 100 % de todos los objetos pertenezcan a la misma clase de almacenamiento, se mostrará dicha clase. Si un bucket contiene objetos de varias clases de almacenamiento, aparecerá la indicación «MIXED». Al hacer clic en «Detalles», se mostrará la distribución relativa entre estas clases.
- Novedad : la clase de almacenamiento óptima recomendada para todos los objetos del depósito.
- Acción : Recomendación sobre el recurso. La recomendación puede ser una de las siguientes

| Recomendación | Descripción |
| --- | --- |
| Dimensionar correctamente | Cambia el tamaño al tipo de recurso especificado en la columna «Nuevo». |
| Ninguna acción | Por defecto, no se recomienda ninguna acción, pero es posible que en el panel «Detalles» haya recomendaciones adicionales con niveles de riesgo más elevados. |

Exportar recomendaciones a un archivo de Excel

Para exportar las recomendaciones a un archivo de Excel, selecciona «Exportar ». Ten en cuenta que el archivo de Excel incluirá varias columnas adicionales, como «región», «tipo de ubicación» y otras.

Detalles de la recomendación

Para ver los detalles de la recomendación de un recurso concreto, selecciona «Ver detalles» en el menú «Más opciones» (tres puntos).

El panel de detalles de GCS muestra la siguiente información:

Recomendaciones

Muestra una o varias recomendaciones, ordenadas según el ahorro de costes y el riesgo (0-5).

- Ahorro: Porcentaje de ahorro estimado para el periodo de 10 o 30 días.
- Ahorro de costes : importe estimado del ahorro.
- Clase de almacenamiento : Clase de almacenamiento recomendada.
- Acción : Acción recomendada.
- Riesgo : En una escala del 0 al 5, el número de transiciones de clase de almacenamiento de acceso frecuente a acceso poco frecuente.

Gráficos

- Tamaño de almacenamiento (bytes) : muestra el tamaño de almacenamiento por clase de almacenamiento. Los valores posibles son los siguientes:
  - Standard
  - Nearline
  - Coldline
  - Archive
  - Autoclass
- Operaciones (recuento de operaciones de clase B/clase A) : muestra el recuento de operaciones de clase A y clase B realizadas en el bucket. Este gráfico ofrece información valiosa sobre la categoría de uso del bucket, como si se trata principalmente de lecturas, de un uso equilibrado entre lecturas y escrituras o de un uso orientado a la escritura.
- Número de objetos (recuento) : El gráfico muestra el número de objetos en el depósito a lo largo del periodo de tiempo.
- Datos transferidos (bytes) : volumen de tráfico saliente hacia Internet (o datos transferidos entre regiones).
- Datos transferidos (bytes) : Cantidad de datos entrantes procedentes de Internet (o datos transferidos entre regiones).
- Eliminación anticipada (bytes/mes) : Cantidad de datos eliminados de los niveles en los que existe un período mínimo de retención.

Poner en práctica las recomendaciones

Clases de almacenamiento

Para cambiar la clase de almacenamiento de los objetos o configurar la optimización del almacenamiento a nivel de depósito, dispone de varias opciones:

- Gestión del ciclo de vida de los objetos

  Puede configurar reglas de gestión del ciclo de vida a nivel de depósito para trasladar automáticamente los objetos a la clase de almacenamiento recomendada en función de su antigüedad, fecha de creación u otras condiciones.

  Para obtener más información sobre la gestión del ciclo de vida de los objetos, consulte [https://cloud.google.com/storage/docs/lifecycle](https://cloud.google.com/storage/docs/lifecycle "(se abre en una pestaña o una ventana nueva)").
- Autoclass

  Habilita Autoclass en los buckets para que los objetos cambien automáticamente de una clase de almacenamiento a otra en función de los patrones de acceso, lo que elimina la necesidad de establecer reglas de ciclo de vida manualmente.

  Para obtener más información sobre Autoclass, consulte [https://cloud.google.com/storage/docs/autoclass](https://cloud.google.com/storage/docs/autoclass "(se abre en una pestaña o una ventana nueva)").

Comprender Autoclass

Autoclass es una función a nivel de bucket que cambia automáticamente los objetos de una clase de almacenamiento a otra en función de los patrones de acceso. Cuando está activado, Autoclass supervisa los patrones de acceso de cada objeto y traslada automáticamente los objetos entre las clases de almacenamiento Estándar, Nearline, Coldline y Archivo, a cambio de una tarifa de supervisión por objeto que se suma a las tarifas específicas de cada clase de almacenamiento.

El ajuste del tamaño de los buckets te ayuda a identificar cuáles se beneficiarán de esta función. Aunque la mayoría de los objetos se crean inicialmente en la clase Estándar, a medida que tus buckets de GCS se vayan optimizando con el tiempo, es posible que se te sugieran recomendaciones de optimización adicionales, como Nearline, Coldline o incluso Archive.

Para obtener más información, consulte [https://docs.cloud.google.com/storage/docs/autoclass](https://docs.cloud.google.com/storage/docs/autoclass "(se abre en una pestaña o una ventana nueva)").

**Tema principal:** [Redimensionamiento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
