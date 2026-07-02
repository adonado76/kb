---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Azure Blob Storage"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto"
source_path: "product/rightsizing-for-azure-blob-storage.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Azure Blob Storage

Puede utilizar el panel de control de Rightsizing para ver las recomendaciones de optimización para Azure Blob Storage. El panel muestra recomendaciones tanto sobre el ajuste de recursos como sobre la inactividad, y permite consultar las recomendaciones de varias suscripciones desde un único panel.

[Ajuste de plantilla en Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Azure Blob Storage resumen

Azure Blob Storage es la solución de almacenamiento de objetos de Microsoft Azure, organizada en torno a contenedores. Los contenedores son entidades de primer nivel dentro de las cuentas de almacenamiento. Puedes utilizar contenedores para almacenar blobs asociados a un nivel de acceso y organizarlos jerárquicamente dentro de directorios virtuales.

Contenedores

En cada contenedor, puedes almacenar un número ilimitado de blobs. Los costes se basan en el nivel de acceso del blob, el almacenamiento asignado (GB al mes), las operaciones (lectura, escritura, listado), las operaciones de recuperación en los niveles Cool, Cold y Archive, las operaciones de rehidratación en el nivel Archive y el volumen de transferencia de datos (salida).

Niveles de acceso

Los niveles de acceso están diseñados para adaptarse a distintos patrones de acceso y necesidades de durabilidad, desde datos a los que se accede con frecuencia hasta almacenamiento de archivo al que se accede con poca frecuencia. Los blobs de un mismo contenedor pueden asignarse a diferentes niveles de acceso.

Azure Blob Storage Los niveles de acceso difieren en cuanto a precio, rendimiento, disponibilidad y requisitos mínimos de duración del almacenamiento. Dependiendo del nivel de acceso, pueden aplicarse tarifas adicionales por las operaciones de recuperación y por la eliminación anticipada cuando los blobs se eliminan, se sobrescriben o se trasladan antes de que se haya cumplido el período mínimo de almacenamiento.

De forma predeterminada, los blobs de Azure se crean en el nivel de acceso «Hot». Para optimizar manualmente cada blob, es necesario identificar las tarifas regionales de cada nivel de acceso, recopilar datos históricos sobre patrones de acceso y operaciones, y evaluar las ventajas e inconvenientes, incluidas las tarifas por eliminación anticipada.

Antes de empezar

Para ver el panel de control de « Azure Blob Storage », asegúrate de haber vinculado Cloudability a las suscripciones correctas de Azure y de haber configurado los ajustes de supervisión y diagnóstico de Azure.

Nota:

Azure Se requieren los ajustes de monitorización y diagnóstico para las recomendaciones de optimización de recursos de « Azure Blob Storage ». El seguimiento de la «hora del último acceso» debe habilitarse explícitamente en las cuentas de almacenamiento para que se puedan generar recomendaciones basadas en los patrones de acceso. Para obtener información sobre cómo conectar Azure con Cloudability, consulta «[Conectarse con Microsoft Azure](../admin/azure-cm-setup.html) ».

Acceder al panel de control de « Azure Blob Storage »

Para acceder al panel de control de Azure Blob Storage, abre la página de inicio de Cloudability. En el menú de navegación de la izquierda, selecciona «Optimizar» > «Ajuste de tamaño ». En la página «Rightsizing», seleccione la pestaña « Azure » y, a continuación, seleccione la subpestaña «Blob Storage ».

Nota:

Solo se muestran los contenedores cuyos costes incurridos sean superiores a cero.

Cada día, Cloudability analiza las métricas de coste, consumo y utilización de Azure Blob Storage correspondientes a los últimos 30 días. Rightsizing ofrece información detallada a nivel de contenedor y recomendaciones de optimización. El gasto se calcula en función de los meses-GB.

Nota:

Los recursos inactivos o los volúmenes de almacenamiento asignados que contienen datos insignificantes o ninguno también se muestran en el panel de control de Rightsizing.

Personalizar el panel de control

Puedes utilizar las siguientes opciones para personalizar tu panel de control.

Seleccionar suscripción

Por defecto, el panel muestra recomendaciones para todas las suscripciones. Para ver las recomendaciones de una suscripción concreta, selecciona el nombre de la suscripción en el menú desplegable «Suscripción ».

Aplicar filtros

Puedes añadir filtros para incluir o excluir datos en función de una o varias condiciones.

Añadir un filtro

Para añadir un filtro:

1. Selecciona «Añadir filtro» en la barra de herramientas.
2. En el menú «Añadir filtro», selecciona una dimensión.
3. Selecciona un operador para establecer una condición lógica.
4. Elige un valor para afinar el filtro.
5. Selecciona «Añadir filtro» para aplicar el nuevo filtro a la página.

Aplicar filtros con enlaces

También puedes añadir filtros seleccionando los valores con hipervínculos azules de la tabla principal. La regla de filtrado se aplica automáticamente al campo «Filtros ». Solo puedes seleccionar un valor o parámetro de cada columna a la vez.

Eliminar un filtro

Para eliminar un filtro: Selecciona la «X» situada junto al filtro que quieras eliminar.

Tabla de recomendaciones para la optimización de la plantilla

El panel de control incluye una tabla con recomendaciones de ajuste de recursos, que ofrece una visión general de los recursos de su servicio « Azure Blob Storage ». La tabla incluye las siguientes columnas:

Nota:

De forma predeterminada, los datos se ordenan según la columna «Ahorro de costes ». Para cambiar el orden de clasificación, solo tienes que seleccionar el nombre de la columna.

- Nombre del contenedor : El nombre del contenedor « Azure Blob Storage ».
- Nombre de la cuenta de almacenamiento : El nombre de la cuenta de almacenamiento de Azure.
- Grupo de recursos : el grupo de recursos de Azure que contiene la cuenta de almacenamiento.
- Suscripción : El identificador de la suscripción « Azure ».
- Tamaño : El tamaño de todos los blobs que hay dentro del contenedor.
- Blobs : El número de blobs que hay en el contenedor.
- Operaciones : número de operaciones (lectura, escritura, listado) realizadas a través del portal o la API.
- Coste : el coste incurrido durante los últimos 30 días por los blobs del contenedor.
- Actual : El nivel de acceso derivado para el contenedor. Si el 100 % de los blobs se encuentran en el mismo nivel de acceso, se muestra dicho nivel. Si un contenedor contiene blobs en varios niveles de acceso, se muestra «MIXED ». Seleccione los datos para ver la distribución relativa en estos niveles.
- Novedad : el nivel de acceso óptimo recomendado para todos los blobs del contenedor.
- Acción : La recomendación sobre el recurso. La recomendación puede ser una de las siguientes:

| Recomendación | Descripción |
| --- | --- |
| Dimensionar correctamente | Pásate al nivel de acceso indicado en la columna «Nuevo ». |
| Ninguna acción | Por defecto, no se recomienda ninguna acción, pero es posible que en el panel de detalles haya recomendaciones adicionales con niveles de riesgo más elevados. |

Exportar recomendaciones a un archivo de Excel

Para exportar las recomendaciones a un archivo de Excel, selecciona «Exportar ». El archivo de Excel incluye columnas adicionales, como «región», «ubicación» y «puntuación de confianza».

Detalles de la recomendación

Para ver los detalles de una recomendación sobre un recurso, selecciona «Ver detalles» en el menú «Más opciones».

El panel de detalles de « Azure Blob Storage » muestra la siguiente información:

Recomendaciones

Se muestran una o varias recomendaciones, clasificadas según el ahorro de costes y el riesgo (0-5).

- Ahorro: Porcentaje de ahorro estimado para el periodo de 30 días.
- Ahorro de costes : Importe estimado del ahorro (una vez deducidos los gastos por cancelación anticipada).
- Nivel de acceso : Nivel de acceso recomendado.
- Acción : Acción recomendada.
- Riesgo : En una escala del 0 al 5, el número de transiciones en el nivel de acceso, pasando de un acceso frecuente a uno poco frecuente.
- Plazo de amortización : tiempo necesario para recuperar los gastos por cancelación anticipada (si procede).
- Puntuación de confianza : nivel de confianza de la recomendación (0-100 %) basado en la exhaustividad de los datos y la disponibilidad de la hora del último acceso.

Gráficos

- Tamaño de almacenamiento (GB) : muestra la capacidad de almacenamiento por nivel de acceso. Los valores posibles son los siguientes:
  - Calor
  - Fresco
  - Frío
  - Archive
  - Nivel Smart
- Operaciones (Recuento de operaciones de lectura/escritura): Muestra el recuento de operaciones de lectura y escritura realizadas en el contenedor. Este gráfico ofrece información valiosa sobre la categoría de uso del contenedor, como si se trata principalmente de lecturas, de un uso equilibrado entre lectura y escritura, o de un uso orientado a la escritura.
- Número de blobs (recuento) : El gráfico muestra el número de blobs en el contenedor a lo largo del periodo de tiempo.
- Datos transferidos (GB) : Cantidad de tráfico saliente hacia Internet (o datos transferidos entre regiones).
- Volumen de recuperación (GB) : Cantidad de datos recuperados de los niveles «Cool», «Cold» o «Archive».
- Operaciones de rehidratación (número) : número de operaciones de rehidratación del nivel de archivo por prioridad (estándar/alta).
- Eliminación anticipada (GB/mes) : Cantidad de datos eliminados de los niveles en los que existe un período mínimo de retención.

Poner en práctica las recomendaciones

Niveles de acceso

Para cambiar el nivel de acceso de los blobs o configurar la optimización del almacenamiento a nivel de contenedor, dispone de varias opciones:

- Gestión del ciclo de vida

  Puede configurar reglas de gestión del ciclo de vida a nivel de la cuenta de almacenamiento para trasladar automáticamente los blobs al nivel de acceso recomendado en función de la antigüedad del blob, la fecha de la última modificación u otras condiciones.

  Para obtener más información sobre la gestión del ciclo de vida, consulte [Azure Blob Storage lifecycle management](https://learn.microsoft.com/en-us/azure/storage/blobs/lifecycle-management-overview "(se abre en una pestaña o una ventana nueva)").
- Nivel Smart

  Active Smart Tier en los contenedores para que los blobs pasen automáticamente de un nivel de acceso a otro (Hot, Cool y Cold) en función de los patrones de acceso, lo que elimina la necesidad de establecer reglas de ciclo de vida manualmente.

  Para obtener más información sobre Smart Tier, consulta «[Niveles de acceso](https://learn.microsoft.com/en-us/azure/storage/blobs/access-tiers-overview#smart-tiering "(se abre en una pestaña o una ventana nueva)") de Azure Blob Storage ».

Entender el sistema Smart Tier

Smart Tier es una función a nivel de contenedor que cambia automáticamente los blobs de un nivel de acceso a otro en función de los patrones de acceso. Cuando está activado, Smart Tier supervisa los patrones de acceso de cada blob y los traslada automáticamente entre los niveles de acceso «Hot», «Cool» y «Cold», por una tarifa de supervisión que se suma a las tarifas específicas de cada nivel.

El ajuste del tamaño a nivel de contenedor te ayuda a identificar qué contenedores pueden beneficiarse de esta función. Los nuevos blobs se crean en el nivel Hot. Smart Tier los traslada automáticamente al nivel «Cool» tras 30 días de inactividad y al nivel «Cold» tras 90 días de inactividad. Al acceder a un blob, este vuelve al nivel «Hot» y se reinicia el ciclo.

Smart Tier no es compatible con el nivel de archivo. Para los datos de archivo a largo plazo, utilice la selección manual de niveles o las políticas de ciclo de vida. Los blobs de menos de 128 KiB permanecen en el nivel Hot y están exentos de las tarifas de supervisión.

Nota:

Smart Tier cobra una tarifa de supervisión de 0.04 por cada 10 000 blobs al mes para los blobs de más de 128 KiB. No se aplican comisiones por cancelación anticipada ni gastos de recuperación en los cambios de plan Smart Tier. Todas las operaciones de acceso se facturan según las tarifas del nivel «Hot».

Para obtener más información, consulta [«Smart tiering» en Azure Blob Storage](https://learn.microsoft.com/en-us/azure/storage/blobs/access-tiers-overview#smart-tiering "(se abre en una pestaña o una ventana nueva)").

Entender las comisiones por cancelación anticipada

Azure Blob Storage cobra tasas por eliminación anticipada cuando se eliminan, sobrescriben o mueven los blobs antes de que se haya cumplido el periodo mínimo de almacenamiento establecido para los niveles Cool (30 días), Cold (90 días) o Archive (180 días). Estas tarifas se prorratean en función de los días que quedan del periodo de duración mínima.

Cloudability Se recomienda tener en cuenta las comisiones por cancelación anticipada al calcular el ahorro previsto y los plazos de amortización. Las recomendaciones que conllevan importantes comisiones por cancelación anticipada incluyen un periodo de amortización, que indica cuánto tiempo se tarda en recuperar los costes iniciales mediante el ahorro continuo.

Para obtener más información sobre las tarifas por cancelación anticipada, consulte [los niveles de acceso](https://learn.microsoft.com/en-us/azure/storage/blobs/access-tiers-overview "(se abre en una pestaña o una ventana nueva)") de Azure Blob Storage.

Seguimiento de la última hora de acceso

El seguimiento de la hora del último acceso debe habilitarse explícitamente en las cuentas de almacenamient Azure es para poder ofrecer recomendaciones basadas en los patrones de acceso. Cuando no se dispone de la «Hora del último acceso», « Cloudability » utiliza la «Hora de la última modificación» para realizar análisis basados en el tiempo, similares a las políticas de ciclo de vida; sin embargo, las recomendaciones resultantes son menos precisas.

Las recomendaciones basadas en la fecha de última modificación obtienen puntuaciones de fiabilidad más bajas (70-89 %) que las basadas en la fecha de último acceso (90-100 %). En los detalles de la recomendación se indica si está activado el seguimiento de la «Última hora de acceso».

Para obtener más información sobre cómo habilitar la «Hora del último acceso», consulta «[Mover datos en función de la hora del último acceso](https://learn.microsoft.com/en-us/azure/storage/blobs/lifecycle-management-overview#move-data-based-on-last-accessed-time "(se abre en una pestaña o una ventana nueva)") ».

**Tema principal:** [Redimensionamiento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
