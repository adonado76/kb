---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Opciones de visualización de datos"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Tablas"
source_path: "studio/new-uc/reference/report-studio-reference/data-display-options.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Opciones de visualización de datos

**Formato de los números**

El formato numérico determina cómo se muestran los valores numéricos en la tabla. El formato se puede configurar a nivel de métrica (para métricas de modelo), a nivel de columna (para columnas de fórmula) o mediante la función ` NumberFormat `.

|  |  |  |  |
| --- | --- | --- | --- |
| **Tipo de formato** | **Ejemplo de patrón** | **Ejemplo de resultado** | **Notas** |
| Número de referencia | #,### | 5 000 000 | Incluye separador de grupos |
| Moneda (USD) | $#,###,00 | 5 $, 000.00 | Utiliza ¤ para la moneda local |
| Porcentaje | #,###% | 75% | Valor multiplicado por 100 |
| Precisión decimal | #,###,00 | 1, 234.56 | Número de decimales fijo |
| Millones | $#,###M | $5M | Sufijo de abreviatura |
| Sin formato | # | 5000000 | Cifra bruta |

**NumberFormat Sintaxis de la función:**

`=NumberFormat(Table.Column, "$#,###.00")`

**Consejo:** Para aplicar el formato de moneda según la configuración regional del proyecto, utiliza el símbolo universal de la moneda (¤) en lugar de un símbolo de moneda específico.

**Visualización de números negativos**

Los números negativos se pueden mostrar en varios formatos especificando un patrón negativo en la función ` NumberFormat `.

|  |  |  |
| --- | --- | --- |
| **Estilo** | **Patrón** | **Ejemplo de resultado** |
| Signo menos (predeterminado) | #,###;-#,### | -1,000 |
| Paréntesis | #,###;(#,###) | (1 000) |
| Moneda entre paréntesis | $#,###;($#,###) | (1 000 $) |

**Visualización de valores nulos y vacíos**

Los valores vacíos o nulos de las tablas se muestran en blanco de forma predeterminada. Utiliza la función IF para mostrar una alternativa:

`=IF(IsNumeric(Value), Currency(Value), "$0")`

**Filtro de ceros**

Puedes eliminar de las tablas las filas con valores nulos para centrarte en los datos relevantes.

**Para aplicar el filtro de ceros:**

1. Selecciona la tabla y haz clic en la pestaña «Datos».
2. Haz clic en los ceros.
3. Seleccione los informes de los que se deben eliminar los ceros.
4. Pulse Aceptar. Para revertir los cambios, selecciona los informes y haz clic en «Revertir todo».

**Tema principal:** [Componentes del informe: Tablas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
