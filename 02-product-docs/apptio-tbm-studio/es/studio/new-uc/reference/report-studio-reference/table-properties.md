---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Propiedades de la tabla"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Tablas"
source_path: "studio/new-uc/reference/report-studio-reference/table-properties.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Propiedades de la tabla

Accede al cuadro de diálogo «Propiedades» haciendo clic con el botón derecho del ratón en la barra «Total» de la tabla y seleccionando «Propiedades». Las propiedades se organizan en las pestañas «Datos», «General» y «Avanzadas».

**Propiedades de los datos**

|  |  |  |
| --- | --- | --- |
| **Propiedad** | **Descripción** | **Valor predeterminado** |
| Número máximo de filas | Número de filas por página. Controla la paginación. | Valor predeterminado del sistema |
| Ocultar la barra de desplazamiento | Oculta los controles de paginación. Solo se muestran las filas máximas. | Inhabilitado |
| Incluir columnas | Limitar las columnas que se muestran a las seleccionadas. | Todas las columnas |
| Excluir columnas | Ocultar las columnas especificadas. | Ninguna |
| Búsqueda automática | Añade campos de búsqueda debajo de los encabezados de las columnas. | Inhabilitado |

**Propiedades generales**

|  |  |  |
| --- | --- | --- |
| **Propiedad** | **Descripción** | **Valor predeterminado** |
| Nombre | Nombre que aparece en el encabezado de la tabla. | Nombre de tabla |
| Título | Texto descriptivo adicional. Admite HTML (sin enlaces). | Vacío |
| Posición del pie de foto | Ubicación del pie de foto con respecto a la tabla: arriba, abajo, a la izquierda, a la derecha, ocultar. | Ocultar |
| Mostrar encabezado | Muestra el encabezado de la tabla con el nombre. | Habilitada |
| Mostrar borde | Añade un borde alrededor de la tabla. | Habilitada |
| Título del resumen | Ajusta el texto de los títulos largos para que quepa en el ancho de la tabla. | Inhabilitado |

**Propiedades avanzadas**

|  |  |  |
| --- | --- | --- |
| **Propiedad** | **Descripción** | **Valor predeterminado** |
| Actualización automática al finalizar los cálculos | Actualiza la tabla cuando finalizan los cálculos en segundo plano. Disponible únicamente con la política de cálculo de Dynamic Publishing. | Inhabilitado |
| Acortar automáticamente los nombres de las nuevas columnas con puntos | Muestra solo la parte que sigue al punto. E.g., « Data.Cost » aparece como «Coste». | Inhabilitado |
| Líneas por fila | Para tablas con ajuste de texto. Déjelo en blanco para utilizar el valor predeterminado. | Vacío |
| Número máximo de columnas que se pueden mostrar | Número máximo de columnas procesadas de la tabla de origen. | Todos |
| Incluir la columna PK | Incluye la columna de clave principal predeterminada. | Automático |
| Usar alias de columna | Permite una configuración correcta cuando dos objetos comparten nombres de columna. Recomendación: Déjalo seleccionado. | Habilitada |
| Ocultar aviso sobre hidratación | Suprime las advertencias cuando los componentes muestran datos de diferentes contextos (por ejemplo, al comparar unidades de negocio). | Inhabilitado |

**Propiedades de la tabla dinámica (versión anterior)**

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Fila de pivote Col | Columna que contiene los valores de la primera columna de la tabla dinámicos. |
| Pivot Col Col | Columna que contiene los encabezados de las columnas de datos de la tabla dinámica. |
| Punto de inflexión: Val Col | Columna que muestra los valores de las celdas en la tabla dinámica. |

**Tema principal:** [Componentes del informe: Tablas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
