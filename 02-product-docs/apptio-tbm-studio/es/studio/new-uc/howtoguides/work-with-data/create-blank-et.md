---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crear tablas en blanco editables"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Introducción manual de datos"
source_path: "studio/new-uc/howtoguides/work-with-data/create-blank-et.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crear tablas en blanco editables

## Objetivo

Crea una tabla totalmente manual en la que los usuarios introduzcan todas las filas, columnas y datos.

## Cuándo se utiliza

- Datos de referencia de pequeño tamaño que no existen en los sistemas de origen (por ejemplo, categorías de proveedores, tablas de correspondencias personalizadas)
- Tablas de consulta con menos de 500 filas
- Datos que cambian con poca frecuencia y requieren una gestión manual
- Esquemas de clasificación gestionados por los usuarios de la empresa
- Asignaciones puntuales o datos de enriquecimiento

## Cuándo NO utilizarlo

- Conjuntos de datos de gran tamaño (más de 500 filas) que deben proceder de sistemas de origen
- Datos disponibles a través de fuentes automatizadas
- Datos que deben completarse a partir de tablas generadas por el sistema (utilice en su lugar tablas editables completadas)

## Requisitos previos

- Data Studio acceso con permisos para crear tablas
- Conocimiento de las columnas y los tipos de datos necesarios
- Planifica quién se encargará del mantenimiento de los datos

**Tiempo estimado:** 10-15 minutos

## Pasos

1. **Crea la tabla editable**
   - Accede a **Data Studio**
   - En la pestaña **«Inicio»**, en el grupo **«Documento»**, selecciona **«Nuevo» > «Tabla editable»**
   - En el cuadro de diálogo «**Nueva tabla introducida manualmente** », selecciona **«Tabla en blanco»**
   - Introduzca un nombre descriptivo para la tabla editable (por ejemplo, «Categorías de proveedores», «Atributos de centros de coste»)
   - Haz clic **en Aceptar**
2. **Configurar el esquema de la tabla**
   - La tabla editable se abre con una columna de clave principal predeterminada (.PK)
   - Ve a **«Pasos» > «Configurar columnas»** en el flujo de trabajo
   - El sistema muestra el espacio de trabajo de configuración de columnas
3. **Añade columnas a tu tabla**
   - Haz clic en **«Añadir una nueva columna»**
   - Para cada columna que necesites, configura:
     - **Nombre de la columna:** Introduzca un nombre descriptivo (por ejemplo, «Nombre del proveedor», «Categoría»)
     - **Descripción:** Proporcionar información contextual a los usuarios que vayan a introducir datos
     - **Tipo de datos:** Selecciona entre «Etiqueta» (texto), «Numérico», «Fecha» o «Booleano»
     - **Nombre para mostrar:** cómo aparece la columna en los informes (opcional)
4. **Configurar las propiedades de la columna** (opcional, pero recomendable)
   - **Valor predeterminado:** rellenar automáticamente las nuevas filas con un valor inicial
   - **Valor obligatorio:** marca esta casilla para evitar que se guarden filas sin un valor
   - **Permitir solo valores únicos:** garantizar que cada fila tenga un valor distinto
5. **Configurar los menús desplegables** (si es necesario para garantizar la calidad de los datos)
   - Consulte la sección «Configurar menús desplegables y validación» en 3.1.3.3 para obtener instrucciones detalladas
   - Los menús desplegables impiden la introducción de texto libre y garantizan la coherencia de los valores
6. **Revisa tu esquema**
   - Comprueba que los nombres, los tipos y los requisitos de las columnas se ajusten a tus necesidades de datos
   - Asegúrate de que la columna de clave principal (.PK) siga configurada
7. **Guardar y registrarse**
   - Haz clic en **«Guardar»** en la pestaña **«Inicio»**
   - Haz clic en **«Check In»** para que la mesa quede disponible
   - Añade un comentario al registrar la entrada en el que describas la finalidad de la tabla

## Resultados previstos

Ahora tienes una tabla editable vacía con un esquema definido. La tabla aparece en la sección **«Tablas»** del **Explorador de proyectos**, dentro de la carpeta en la que la has creado. Los usuarios pueden añadir datos a través de informes con componentes de tabla editables o mediante la edición directa en Data Studio (para administradores). La tabla está lista para incorporarse a las tablas de transformación y a tu modelo de costes.

## Errores habituales

|  |  |
| --- | --- |
| **Emitir** | **Solución** |
| **Se han definido demasiadas columnas desde el principio** | Empieza solo con las columnas imprescindibles. Puedes añadir más columnas más adelante, según surja la necesidad. Las columnas que no se utilizan confunden a los usuarios que introducen datos. |
| **No está claro para qué sirven las columnas** | Añade siempre descripciones a las columnas. Los usuarios que introducen datos necesitan saber qué representa cada campo. |
| **No hay validación de datos** | Sin validación ni menús desplegables, los usuarios pueden introducir datos incoherentes (por ejemplo, «Servicios de TI», «Servicios de TI», «Tecnología de la información»). Añade menús desplegables a cualquier columna que se utilice en las asignaciones o en las dimensiones de los informes. |
| **Se ha seleccionado un tipo de datos incorrecto** | Si seleccionas «Numérico», pero los usuarios necesitan introducir valores como «N/A» o una combinación de texto y números, la columna rechazará las entradas válidas. Utiliza el tipo «Etiqueta» cuando los datos puedan incluir valores no numéricos. |

## ¿Qué viene ahora?

Una vez creada la tabla en blanco editable:

- [Crear una tabla de transformación a partir de la tabla editable](data-security.html)
- [Configurar la publicación de tablas editables](setup-et-publish.html)
- [Añadir tablas a los informes](../create-reports/add-tables-report.html)
- [Configurar la seguridad a nivel de fila](htg-arls.html)

**Tema principal:** [Introducción manual de datos](../../../../studio/new-uc/howtoguides/work-with-data/manual-data-entry.html)
