---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configuración de validación"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes de los informes: tablas editables en los informes"
source_path: "studio/new-uc/reference/report-studio-reference/validation-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuración de validación

Las reglas de validación garantizan la calidad de los datos al impedir que se introduzcan datos incorrectos. TBM Studio ofrece varios mecanismos de validación.

**Campos obligatorios**

Marca las columnas necesarias para evitar que se guarden filas con valores vacíos:

- Activar el campo «Valor obligatorio» en la configuración de la columna « Data Studio »
- Los usuarios no pueden guardar la tabla si los campos obligatorios están vacíos
- Los campos obligatorios se indican visualmente en la interfaz del informe

**Validación de tipos de datos**

La configuración del tipo de columna aplica una validación básica de los datos:

- **Numérico:** solo admite entradas numéricas en el formato de la configuración regional del proyecto
- **Fecha:** comprueba que las entradas se ajusten al formato de fecha configurado
- **Etiqueta:** Acepta cualquier texto introducido

**Validación del valor único**

Active la opción «Permitir solo valores únicos» para evitar entradas duplicadas en una columna. Esto es imprescindible para las columnas de clave principal o cualquier columna que deba contener valores únicos.

**Validación del menú desplegable**

Cuando se configuran los valores posibles:

- **Permitir valores que no figuran en la lista de valores posibles:** si no está marcado (opción predeterminada), los usuarios deben seleccionar un valor del menú desplegable
- **No permitir la edición en la celda de valores posibles:** si se marca, impide escribir en la celda (útil para controles de selección estrictos)

**Total de validadores**

En el caso de las columnas numéricas, puedes validar los totales de fila o de columna:

- **Validador de totales de columna:** comprueba que los totales de las filas cumplan los criterios (por ejemplo, deben sumar 100 en el caso de las asignaciones porcentuales)
- **Validador de totales de fila:** comprueba que los totales de las columnas se encuentren dentro de los rangos especificados

Configure los validadores haciendo clic en el icono situado junto a «Validar total» en la cinta de «Tablas editables». Selecciona un operador de comparación (=, <, >, <=, >=) e indica el valor de referencia.

**Mensaje de error de validación**

Cuando falla la validación:

- Las celdas no válidas aparecen resaltadas en rojo
- Los mensajes de error aparecen junto a los valores afectados
- Las filas con errores aparecen en la parte superior de la tabla para facilitar su identificación
- Los usuarios pueden guardar el informe aunque contenga errores de validación, pero no pueden publicar datos no válidos

Nota: *Para que la validación avanzada funcione, es necesario activar la función «Habilitar paso de validación para tablas editables» en Configuración del proyecto > Habilitar funciones.*

**Tema principal:** [Componentes de los informes: Tablas editables en los informes](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
