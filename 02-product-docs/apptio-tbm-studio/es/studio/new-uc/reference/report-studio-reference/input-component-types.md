---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Tipos de componentes de entrada"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe - Componentes de entrada"
source_path: "studio/new-uc/reference/report-studio-reference/input-component-types.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tipos de componentes de entrada

TBM Studio permite introducir datos mediante configuraciones editables de las columnas de las tablas. Cada tipo de columna determina cómo introducen los datos los usuarios.

**Introducción de texto**

Las columnas de entrada de texto admiten datos de texto sin formato y se utilizan para etiquetas, descripciones y otros valores no numéricos.

**Configuración**

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Tipo | Establecer como «Etiqueta» para datos de texto sin formato |
| Nombre | Nombre que aparece en el encabezado de la columna |
| Descripción | Texto de ayuda que describe la finalidad de la columna |
| Valor predeterminado | Valor preestablecido para las nuevas filas |
| Valores posibles | Opcional: limitar a una lista controlada (crea un menú desplegable) |

**Notas de uso**

- No se pueden realizar operaciones matemáticas con las columnas de etiquetas
- El ajuste de línea no se aplica a las columnas de fuentes primarias en las tablas editables enriquecidas
- El texto se puede copiar y pegar desde Excel utilizando Control+C / Control+V (Windows) o ⌘+C / ⌘+V (Mac)

**Introducción de datos numéricos**

Las columnas de entrada numérica admiten valores enteros o decimales y se ajustan a la configuración regional del proyecto en lo que respecta al formato de los números.

**Configuración**

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Tipo | Selecciona «Numérico» para los datos numéricos |
| Nombre | Nombre que aparece en el encabezado de la columna |
| Descripción | Texto de ayuda que describe la finalidad de la columna |
| Valor predeterminado | Valor preestablecido para las nuevas filas |
| Valor obligatorio | Si se marca esta casilla, los usuarios no podrán guardar sin introducir un valor |

**Notas de uso**

- Las columnas numéricas admiten el formato específico de cada configuración regional (separadores decimales, separadores de miles)
- El formato de moneda y porcentaje se aplica a nivel del informe, no a nivel de la configuración de las columnas
- Los valores numéricos pueden utilizarse en columnas de fórmulas y cálculos
- La función «Llevar adelante» ( 12.6 y versiones posteriores) permite que los valores numéricos se propaguen a las columnas siguientes

**Introducción de la fecha**

Las columnas de entrada de fecha admiten valores de fecha con formatos de visualización configurables.

**Configuración**

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Tipo | Establecer como fecha para los datos de fecha |
| Formato de fecha | Especifique el formato utilizando los patrones estándar (por ejemplo, MM/dd/aaaa) |
| Nombre | Nombre que aparece en el encabezado de la columna |
| Valor predeterminado | Fecha preestablecida para las nuevas filas |

**Formatos de fecha compatibles**

|  |  |
| --- | --- |
| **Patrón** | **Ejemplo de resultado** |
| dd/mm/aaaa | 15 de enero de 2025 |
| aaaa-MM-dd | 15 de enero de 2025 |
| día del mes, año | 15 de enero de 2025 |
| dd-MM-aa | 15-Jan-25 |

*Nota: La cadena de formato de fecha no debe ir entre comillas al configurar la columna.*

**Campos de selección (menús desplegables)**

Los campos de selección desplegables limitan la introducción de datos a un conjunto controlado de valores, lo que garantiza la coherencia de los datos y reduce los errores de introducción.

**Configuración básica del menú desplegable**

Configure un menú desplegable estableciendo la propiedad «Valores posibles» mediante uno de estos métodos:

**Método 1 - Lista estática: Introduzca una lista de valores separados por comas, como ""OpEx, CapEx, Transfer"**

**Método 2: Lista basada en fórmulas: Consulte los valores de otra tabla utilizando la sintaxis: %nombredetabla/!LIMIT\_COLUMNS[nombre\_columna]**

**Propiedades del menú desplegable**

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Valores posibles | Lista estática o fórmula que define las opciones disponibles |
| Contexto de los valores posibles | Establecer en «Informe» para el contexto estático o en «Fila actual» para el filtrado dinámico |
| Permitir valores que no figuran en la lista de valores posibles | Si se marca esta casilla, los usuarios podrán introducir valores personalizados |
| Desactivar la edición en la celda de valores posibles | Si se marca esta casilla, los usuarios no podrán escribir en la celda |

*Nota: El menú desplegable muestra los primeros 15 valores únicos. En las listas con más de 15 valores, aparece un botón «Buscar».*

**Menús desplegables en cascada (dependientes)**

Crea menús desplegables en los que las opciones disponibles dependan del valor de otra columna utilizando texto dinámico. Por ejemplo, un menú desplegable de ciudades que se filtra en función del estado seleccionado:

- Crea una tabla de origen (por ejemplo, «Estados-Ciudades») con las columnas «Estado» y «Ciudad»
- Configurar los valores posibles de la columna «Estado»: %States-Cities/!LIMIT\_COLUMNS[Estado]
- Configura la columna «Ciudad» con un filtro: %States-Cities/!FILTRO[Estado="<%=Estado%>"]/!LIMIT\_COLUMNS[Ciudad]
- Establecer el contexto de valores posibles de la columna «Ciudad» en la fila actual

**Tema principal:** [Componentes del informe - Componentes de entrada](../../../../studio/new-uc/reference/report-studio-reference/report-component-input-components.html)
