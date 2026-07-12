---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Validación"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe - Componentes de entrada"
source_path: "studio/new-uc/reference/report-studio-reference/validation.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Validación

TBM Studio ofrece varios mecanismos de validación para garantizar la integridad de los datos.

**Validación de campos obligatorios**

Propiedad: Valor obligatorio: si se marca esta casilla, los usuarios no podrán guardar la tabla si alguna fila contiene un valor en blanco en esta columna.

**Validación de tipos de datos**

La propiedad «Type» comprueba automáticamente que los valores introducidos coincidan con el tipo de datos esperado:

|  |  |
| --- | --- |
| **Tipo** | **Validación** |
| Etiqueta | Acepta cualquier texto |
| Numérico | Valida el formato numérico según la configuración regional del proyecto |
| Fecha | Comprueba que el formato de fecha se ajuste al formato de fecha configurado |

**Validación de la unicidad**

Propiedad: Permitir solo valores únicos: si se marca esta opción, los usuarios no podrán guardar la tabla si la columna contiene valores duplicados.

**Validación de rangos (a nivel de tabla)**

Configura la validación de rango a través de las propiedades «Validate Total»:

- Validador de totales de columna: comprueba que los totales de las filas se encuentren dentro de los rangos aceptables
- Validador de totales de fila: comprueba que los totales de las columnas cumplan los requisitos (por ejemplo, que la suma de los porcentajes sea igual al 100 %)

**Mensaje de error de validación**

Cuando falla la validación:

- Los mensajes de advertencia o de error aparecen junto a la celda correspondiente
- Las filas que contienen errores se resaltan y se colocan al principio de la tabla
- Los usuarios pueden guardar y revisar los informes aunque contengan errores (para trabajos en borrador)
- Las filas no válidas no se pueden publicar correctamente en las tablas de transformación

**Tema principal:** [Componentes del informe - Componentes de entrada](../../../../studio/new-uc/reference/report-studio-reference/report-component-input-components.html)
