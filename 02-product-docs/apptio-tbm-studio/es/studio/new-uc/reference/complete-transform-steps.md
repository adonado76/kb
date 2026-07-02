---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Referencia completa de los pasos de transformación"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Data Studio Referencia"
  - "Pasos de la transformación"
source_path: "studio/new-uc/reference/complete-transform-steps.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Referencia completa de los pasos de transformación

**Añadir paso**

**Objetivo:** Añadir filas de una o varias tablas de origen a la tabla de destino

**Cuándo utilizarlo: para** combinar datos de varias fuentes en una sola tabla

**Solo se puede añadir una vez:** Sí

**Comportamiento:**

- Los datos añadidos se incorporan como nuevas filas (las filas nunca se fusionan)
- Las columnas de origen se pueden asignar a columnas de destino ya existentes
- Las columnas de origen se pueden añadir como nuevas columnas a la tabla de destino

**Parámetros:**

|  |  |
| --- | --- |
| **Parámetro** | **Descripción** |
| Añadir fuente de datos | Selecciona las tablas de origen a las que deseas añadir datos |
| Correlación de columnas | Asignar columnas de origen a columnas de destino |
| Columnas de origen adicionales | Añadir columnas de origen que no están en el destino |

**Paso de partición de fechas**

**Objetivo:** Distribuir automáticamente los datos con fecha y hora a lo largo de distintos periodos de tiempo

**Solo se puede añadir una vez:** Sí

**Parámetros basados en filas:**

|  |  |
| --- | --- |
| **Parámetro** | **Descripción** |
| Fecha de inicio | Columna que contiene las fechas de inicio |
| Fecha de finalización | Columna que contiene las fechas de finalización (opcional) |

**Parámetros basados en columnas:**

|  |  |
| --- | --- |
| **Parámetro** | **Descripción** |
| Interpretar «Year» como | Ejercicio fiscal o año natural |
| Nuevo prefijo de columna | Etiqueta añadida a las columnas particionadas |
| Conjuntos de columnas | Selecciona los grupos de columnas que deseas dividir |

**Paso de filtrado**

**Objetivo:** Eliminar filas en función de condiciones de los valores de las columnas

**Solo se puede añadir una vez:** Sí

**Operadores de filtro:**

|  |  |  |
| --- | --- | --- |
| **Operador** | **Tipo de datos** | **Descripción** |
| Contiene | Serie | Coincidencia parcial |
| No contiene | Serie | Exclusión parcial |
| Empieza por | Serie | Coincidencia de prefijo |
| Termina por | Serie | Coincidencia de sufijo |
| Menor que | Numérico | Por debajo del valor |
| Mayor que | Numérico | Mayor que el valor |
| Igual que | Todos los tipos | Coincidencia exacta |
| No igual | Todos los tipos | No igual a |
| Es nulo | Todos los tipos | Valor vacío |
| No es nulo | Todos los tipos | Valor no vacío |
| Está en | Todos los tipos | Coincidencia de varios valores |
| No está en | Todos los tipos | Exclusión múltiple |

**Combinación de filtros:**

- **Y:** Todas las condiciones deben cumplirse
- **O:** Cualquier condición debe ser verdadera
- **Entre paréntesis:** afecciones relacionadas

**Paso de fórmulas**

**Objetivo:** Añadir columnas calculadas, cambiar los tipos de columna o sobrescribir valores existentes

**Operaciones con columnas:**

|  |  |
| --- | --- |
| **Operación** | **Descripción** |
| Añadir columna | Crear una nueva columna calculada |
| Editar columna | Modificar la fórmula o el tipo de una columna existente |
| Suprimir columna | Eliminar una columna de fórmulas |

**Véase también:** Sección «Fórmulas y funciones de 5.4 » para consultar la referencia completa de fórmulas

**Paso en grupo**

**Objetivo:** Agregar datos de una tabla agrupándolos por una o varias columnas

**Solo se puede añadir una vez:** Sí

**Comportamiento:**

- Crea una fila por cada combinación única de valores de agrupación
- Añade una columna « {.Count} » que muestra el recuento de filas por grupo
- Se suman las columnas numéricas
- Las columnas de texto con valores variables muestran «...» (... )

**Únete a Step**

**Objetivo:** Combinar datos de varias tablas basándose en la coincidencia de los valores de las columnas

**Solo se puede añadir una vez:** Sí

**Unión frente a anexión:**

|  |  |
| --- | --- |
| **Unir** | **Añadir** |
| Combina los datos en las mismas filas | Añade datos como nuevas filas |
| Basándose en la coincidencia de los valores de las columnas | Basado en la asignación de columnas |
| Utilizar como enriquecimiento | Se utiliza para combinar conjuntos de datos |

**Paso de columnas del mapa**

***Aplicable a:*** *TBM Studio 12.7 y versiones posteriores*

**Objetivo:** Alinear los datos de las tablas con los esquemas de los conjuntos de datos maestros para garantizar el cumplimiento normativo de la aplicación

**Solo se puede añadir una vez:** Sí

**Opciones de visualización:**

|  |  |
| --- | --- |
| **Opción** | **Descripción** |
| Elegir origen | Selecciona una columna en el menú desplegable |
| Introducir un valor fijo | Valor constante para todas las filas |
| Añadir columna personalizada | Crear una nueva columna en el conjunto de datos maestros |
| Unir | Utilizar columnas de tablas unidas |

**Paso de pivote**

**Objetivo:** Resumir los datos convirtiendo las filas en columnas

**Solo se puede añadir una vez:** Sí

**Parámetros:**

|  |  |
| --- | --- |
| **Parámetro** | **Descripción** |
| Fila de pivote | Columna para los valores de la primera columna |
| Columna pivote | Columna para los encabezados de columna |
| Valor de pivote | Columna numérica que se va a agregar en las celdas |

**Paso: Eliminar duplicados**

**Objetivo:** Eliminar las filas que contengan valores duplicados en las columnas especificadas

**Solo se puede añadir una vez:** Sí

**Parámetros:**

|  |  |
| --- | --- |
| **Parámetro** | **Descripción** |
| Columna de clave | Columna para detectar duplicados |
| Columna de comparación | Columna que se utiliza para determinar qué fila conservar |
| Tipo de comparación | El mayor o el menor: determina qué fila se conserva |

**Paso de seguridad a nivel de fila**

***Aplicable a:*** *TBM Studio 12.2 y versiones posteriores*

**Objetivo:** Filtrar los datos de la tabla en función del usuario actual con fines de gobernanza de datos

**Solo se puede añadir una vez:** Sí

**Parámetros de búsqueda:**

|  |  |
| --- | --- |
| **Campo** | **Descripción** |
| Primer campo | Columna de la tabla que se va a filtrar |
| Segundo campo (intersecciones) | Tabla de correspondencias con datos de seguridad |
| Tercer campo | Columna de la tabla de correspondencias con los valores permitidos |
| Cuarto campo (donde se encuentra el usuario) | Columna de la tabla de correspondencias con los ID de usuario |

**Paso de despivotado**

**Objetivo:** Convertir los valores de una columna en filas adicionales

**Solo se puede añadir una vez:** Sí

**Columnas de salida:**

|  |  |
| --- | --- |
| **Columna** | **Descripción** |
| Ocultar columna | Nombres originales de los encabezados de las columnas |
| Ocultar valor | Valores originales de las columnas |

**Avisos:**

- Evita mezclar tipos de columna en columnas sin pivotar
- Controla si se produce una expansión excesiva de las filas (las filas se multiplican por el número de columnas)

**Tema principal:** [Pasos de la transformación](../../../studio/new-uc/reference/transform-steps.html)
