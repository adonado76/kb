---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Opciones de edición de columnas"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes de los informes: tablas editables en los informes"
source_path: "studio/new-uc/reference/report-studio-reference/column-editing-options.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Opciones de edición de columnas

Cada columna de una tabla editable se puede configurar con comportamientos de edición específicos. Estos ajustes se definen en Data Studio, pero influyen en el comportamiento de la columna en el componente de informe.

**Configuración editable frente a configuración de solo lectura**

Las columnas se pueden configurar como editables o de solo lectura a nivel de informe:

- **Columnas no editables:** Accede a la cinta «Tablas editables» y despliega la sección «Columnas no editables» para seleccionar las columnas que deben ser de solo lectura
- **Columnas de origen:** en las tablas editables enriquecidas, las columnas de la transformación de origen son de solo lectura por defecto
- **Permitir la edición en las columnas incluidas:** una casilla de verificación en la configuración permite editar las columnas de origen incluidas

**Tipos de entrada**

Los tipos de datos de las columnas determinan la experiencia de introducción de datos:

|  |  |  |
| --- | --- | --- |
| **Tipo de entrada** | **Descripción** | **Data Studio Escenario** |
| Texto (Etiqueta) | Introducción de texto libre | Tipo: Etiqueta |
| Número (numérico) | Valores numéricos con formato regional | Tipo: Numérico |
| Desplegable | Selección entre valores predefinidos | Valores posibles configurados |
| Fecha | Selector de fecha con control de formato | Tipo: Fecha con formato de fecha |
| Booleano | Selección de casillas de verificación «Verdadero/Falso» | Tipo: Booleano |

**Fuentes de valores del menú desplegable**

Los menús desplegables se pueden configurar con valores estáticos o dinámicos:

- **Lista estática:** valores separados por comas introducidos directamente (por ejemplo, « "OpEx,CapEx, Transfer»)
- **Dato dinámico de una tabla:** Fórmula que hace referencia a otra tabla: %TableName/!LIMIT\_COLUMNS[ ColumnName ]
- **Menús desplegables en cascada:** Filtra los valores en función de otra columna utilizando: %Table/!FILTRO[ Column="<%=OtherColumn%>" ]/!LIMIT\_COLUMNS[Columna]

La configuración «Valores posibles» determina cómo se evalúa el texto dinámico: la opción «Fila actual» evalúa las fórmulas en el contexto de la fila que se está editando, mientras que la opción «Informe» las evalúa en el contexto general del informe.

**Valores predeterminados**

Cuando los usuarios añaden nuevas filas, se pueden rellenar previamente los valores predeterminados:

- Establecer en el campo «Valor predeterminado» de la configuración de una columna de « Data Studio »
- Pueden ser valores fijos o fórmulas
- Útil para establecer fechas predeterminadas, valores de estado o asignaciones de propietarios

**Tema principal:** [Componentes de los informes: Tablas editables en los informes](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
