---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Conceptos básicos de la tabla de compromisos"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Comprender los conceptos básicos de la gestión de compromisos en Cloudability"
source_path: "product/commitment_table_basics.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conceptos básicos de la tabla de compromisos

## Finalidad

El objetivo de este documento es presentar cómo se muestran los metadatos en las páginas de compromisos y explicar los datos que se muestran en las tablas de compromisos de Cloudability y cómo leerlos, filtrarlos y exportarlos de forma coherente en todas las páginas (Gestor, Cartera, Recomendaciones). Se trata de una referencia práctica para las columnas, la clasificación y la interpretación.

## Arquitectura de la información

Los metadatos de compromisos, recomendaciones y grupos aparecen en tres patrones de interfaz de usuario en toda la aplicación:

**Tabla** - Una cuadrícula tabular con columnas y grupos de columnas (cabeceras) que organizan los campos relacionados para facilitar la comparación.

**Panel de detalles (cajón derecho)** - Un panel deslizante que muestra las propiedades a nivel de campo y acciones contextuales para la fila o tarjeta seleccionada.

**Tarjeta de resumen** : tarjeta a nivel de página que muestra las métricas o atributos clave relevantes para la vista actual (se suele utilizar en la página Recomendaciones).

Por qué es importante: los patrones de visualización estandarizados hacen que la información sea escaneable, alinean la terminología del Centro de ayuda con la interfaz de usuario del producto y garantizan la coherencia de los informes y análisis de todos los proveedores.

## Componentes de la interfaz de usuario

**Gestor de compromisos** - Visión general a nivel agregado con un gráfico de series temporales de los costes y ahorros de los compromisos. En el futuro, añadiremos una tabla desplegable mensual para resumir los costes periodificados que se muestran en el gráfico.

**Cartera de compromisos** - Un inventario tabular de los compromisos. Cada fila incluye una acción Detalles (alineada a la derecha) que abre el panel Detalles (cajón derecho) para mostrar los campos no presentes en la tabla.

**Recomendaciones de Compromiso** - Una vista resumida que refleja las interacciones de la Cartera. La acción Detalles abre una Página de detalles específica (en lugar del cajón). Una tarjeta de resumen destaca los supuestos de recomendación (plazo, alcance, reparto, pago) y los KPI modelados, como el coste y el ahorro neto.

Por qué es importante: Estamos definiendo una nomenclatura coherente para estos componentes de la interfaz de usuario (Tabla, Panel de detalles, Tarjeta de resumen, Página de detalles) para explicar con mayor eficacia los conceptos más adelante en esta documentación.

## Datos de referencia

La siguiente tabla proporciona una referencia para cada campo que aparece en las páginas de compromiso.

*Detalles del compromiso*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Campo** | **AWS** | **GCP** | **AZURE** | **Notas** |
| ID de compromiso | ID | ID | — | Identificador único para el registro de compromisos. |
| Categoría | Categoría | Categoría | — | Categoría agnóstica de proveedor (por ejemplo, Recursos frente a Gastos). |
| Servicio | Servicio | Servicio | — | Familia de servicios o productos (por ejemplo, EC2, CME, RDS ). |
| Región | Región / Zona de disponibilidad | Región | — | Ubicación de un recurso. |
| Plazo | Plazo | Plazo | — | Normalmente, 1 o 3year. |
| Opción de pago / Frecuencia de facturación | Opciones de pago | — | — | AWS : No/Parcial/Todo por adelantado. GCP : prácticamente sin pago inicial para la mayoría de los compromisos. |
| Coste inicial | Coste inicial | — | — | Reconocido por base (efectivo vs. ajustado). |
| Importe del compromiso por hora | Importe por hora | Importe por hora | — | En el contexto del compromiso, por ejemplo, GCP : los CUD de recursos muestran vCPU/Memory/SSD/GPU las cantidades; AWS EC2 : el RI muestra el recuento o la cantidad. |
| Lista de compromisos Tipo de descuento | — | Tasa de ahorro de la lista | — | Tipo de descuento publicado para el artículo. |
| SO | SO | — | — | Aplicable a algunos compromisos de cálculo. |
| Tenencia | Tenencia | — | — | Tenencia dedicada frente a tenencia compartida ( AWS ). |
| Clase | Clase | — | — | Estándar frente a convertible (si procede). |
| Compartiendo | ISF | — | — | Indicador de flexibilidad / compartición del tamaño de la instancia ( AWS ). |
| Unidades (obsoletas) | unidades | — | — | Ya no es necesario. |
| Compartir región Bool | MultAZ | — | — | Indica el comportamiento de compartir multiAZ/region ( AWS ). |
| Tipo de motor | Tipo de motor | — | — | Aplicable a determinados productos de base de datos/búsqueda. |

*Cuenta y propiedad*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Campo** | **AWS** | **GCP** | **AZURE** | **Notas** |
| Nombre de la cuenta del pagador | Cuenta del pagador | Cuenta de facturación | — | Propietario de la factura / contexto de facturación. |
| ID de la cuenta del pagador | — | ID de cuenta de facturación | — | Identificador de la cuenta de facturación ( GCP ). |
| Nombre de la cuenta vinculada | Cuenta enlazada | Proyecto | — | Cuenta/proyecto consumidor. |
| ID de cuenta vinculada | — | ID de proyecto | — | Identificador del proyecto ( GCP ). |

*Rendimiento ( NonKPI Fields)*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Campo** | **AWS** | **GCP** | **AZURE** | **Notas** |
| coste de compromiso [notificado | Coste | Coste | — | Coste total de los compromisos en el ámbito/periodo seleccionado. |
| [Pagado] Coste de compromiso | Coste pagado | Coste pagado | — | Reconocido por base (efectivo frente a ajustado). |
| coste de compromiso [de por vida | Coste de por vida | Coste de por vida | — | Coste acumulado a lo largo de la vida del compromiso. |
| Compromiso comunicado Ahorro neto | Ahorro neto | Ahorro neto a lo largo de la vida | — | Puede haber diferencias en la denominación; refleja la distinción entre «período» y «vida útil» en GCP. |
| Tasa de ahorro comprometida comunicada | Tasa de ahorro | Tasa de ahorro | — | Tasa de ahorro actual para el ámbito de la fila (no es un KPI de cartera). |
| Utilización de los compromisos comunicados | Consumo | Consumo | — | Utilización combinada de la fila (no es un KPI de cartera). |
| coste [restante] del compromiso | Coste restante | Coste restante | — | Exposición a plazo hasta el vencimiento. |
| Ahorro neto no realizado comunicado | Ahorro neto no realizado | — | — | Ahorro potencial aún no realizado debido a la infrautilización. |
| Por hora OnDemand Compromiso | — | OnDemand compromiso | — | GCP valor de referencia para la comparación (cuando esté disponible). |
| Ahorro neto por hora | — | Ahorro neto (por hora) | — | Cuando se exponen con una granularidad horaria. |
| Punto de equilibrio | — | Punto de equilibrio (meses) | — | Meses para alcanzar el punto de equilibrio con el uso actual. |

*SubQuantities (CUD de recursos de GCP )*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Campo** | **AWS** | **GCP** | **AZURE** | **Notas** |
| Importe del compromiso horario - Núcleos | — | Cantidad comprometida por hora (núcleos) | — | vCPU cantidad comprometida. |
| Utilización - Núcleos | — | Utilización (núcleos) | — | vCPU utilización de la cantidad comprometida. |
| Importe del compromiso por hora - Memoria | — | Importe de compromiso por hora (memoria) | — | Memoria ( GiB ) cantidad comprometida. |
| Utilización - Memoria | — | Utilización (memoria) | — | Utilización de la memoria de la cantidad comprometida. |
| Importe del compromiso por hora - SSD | — | Importe del compromiso por hora (SSD) | — | Cantidad de SSD comprometida. |
| Importe del compromiso por hora - GPU | — | Importe del compromiso por hora (GPU) | — | Cantidad de GPU comprometida. |

*Detalles de la recomendación (si procede)*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Campo** | **AWS** | **GCP** | **AZURE** | **Notas** |
| Recomendación SubType | Familia de instancias / Nodo / Tipo de instancia | Tipo de máquina | — | Forma/familia propuesta para la recomendación. |
| Recomendación mensual Crédito SUD | — | Recomendación Crédito de descuento por uso continuado (estimación mensual) | — | GCP presupuesto concreto. |
| Recomendación de por vida Crédito SUD | — | Recomendación Crédito de descuento por uso sostenido (estimado de por vida) | — | GCP presupuesto concreto. |

*Estado e interfaz de usuario*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Campo** | **AWS** | **GCP** | **AZURE** | **Notas** |
| Estado | Estado | — | — | Estado actual (activo, jubilado, etc.). |
| Fecha de inicio | Fecha de inicio | — | — | Comienzo efectivo. |
| Fecha de finalización | Caducidad | — | — | Fin efectivo / expiración. |
| Detalles Botón | Detalles Icono | Detalles Icono | — | Control de interfaz de usuario para abrir la página de cajones/detalles. |
| Número total de compromisos | Compromisos | — | — | Etiqueta encima de la tabla junto al icono de exportación (etiqueta UI). |

## Trabajar con la mesa

**Barra de filtros** : filtre manualmente los metadatos mediante la barra de herramientas de filtros comunes.

**Filtrar Hipervínculo** - Las celdas hipervinculadas en la tabla están inmediatamente disponibles para filtrar como 'iguales'. Seleccione un hipervínculo para filtrar la tabla por este valor. El chip de filtro aparecerá en la barra de herramientas de filtros de arriba.

**Mostrar/ocultar columnas** : utilice la barra Mostrar/ocultar columnas situada a la derecha de la tabla para seleccionar las columnas que desea ver. (Próximamente)

**Ordenar y MultiSort** - Haga clic en un encabezado para ordenar de forma descendente. Haga clic de nuevo para ordenar de forma ascendente. Haga clic una tercera vez para volver al estado por defecto.

**Exportar** : el botón «Exportar» permite obtener un archivo « CSV » con los datos de la tabla en formato «lo que ves es lo que obtienes». Tenga en cuenta que todos los metadatos se incluyen en esta exportación.

## Para llevar

Es fundamental familiarizarse con las tablas, etiquetas y diseños utilizados en la Gestora de compromisos, la cartera y las recomendaciones. Con un vocabulario coherente (tabla, panel de detalles, tarjeta de resumen, página de detalles) y una asignación clara de los nombres de los campos en todos los proveedores, podrá:

- Leer las líneas en su contexto (ámbito, plazo, pago), evitando interpretaciones erróneas.
- Trazar correctamente la propiedad y el reparto (pagador/cuenta de facturación frente a cuenta/proyecto vinculado).
- Comparación entre nubes utilizando campos normalizados.
- Pase más rápidamente de lo que ve (tabla) a por qué es importante (detalles, subcantidades, campos de rendimiento) y qué hacer a continuación (filtros, exportación y Recomendaciones).

Con esta información básica, la documentación posterior profundizará en la aplicación y en cómo se utiliza para optimizar el gasto en la nube.

**Tema principal:** [Comprender los fundamentos de la gestión de los compromisos en Cloudability](../product/commitment_management_basics.html)
